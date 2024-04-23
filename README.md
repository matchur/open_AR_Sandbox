# Open AR-Sandbox

* Check the complete and up-to-date documentation on [read the docs](https://open-ar-sandbox.readthedocs.io/en/latest/)


Bem vindo ao Open AR-Sandbox Repositório. Esse repositório é um fork do projeto original [Open AR-Sandbox](https://github.com/cgre-aachen/open_AR_Sandbox/) contendo algumas modificações, dentre elas a documentação e a tradução para a linguagem portuguesa brasileira.

Seja bem vindo ao repositório do Open AR-Sandbpx. Se você ainda não conhece sobre o projeto fique a vontade de uma olhada nesses videos:
[![A Sandbox CGRE em ação](https://img.youtube.com/vi/oE3Atw-YvSA/0.jpg)](https://www.youtube.com/watch?v=oE3Atw-YvSA)

[![O que é uma caixa de areia de RA?](https://img.youtube.com/vi/RIvYO1lx6vs/0.jpg)](https://www.youtube.com/watch?v=RIvYO1lx6vs)

![Python 3](https://img.shields.io/badge/Python-3-blue.svg)
[![Licença: LGPL v3](https://img.shields.io/badge/Licença-LGPL%20v3-blue.svg)](https://www.gnu.org/licenses/lgpl-3.0)

Sumário
--------
* [Introdução](README.md#introdução)
* [Recursos](README.md#recursos)
* [Licença, uso e atribuições](README.md#licença-uso-e-atribuição)
* [Requisitos](README.md#requisitos)
* [Instalação](README.md#instalação)
    * [Pacotes padrão](README.md#pacotes-padrão)
    * [Download de dados de exemplo](README.md#download-de-dados-de-exemplo)
    * [Instalação do Kinect](README.md#instalação-do-kinect)
        * [Windows](README.md#para-windows)
            * [KinectV2 - PyKinect2](README.md#kinect-v2---pykinect2)
        * [Linux](README.md#para-linux)
            * [KinectV1 - libkinect](README.md#kinect-v1---libfreenect)
            * [KinectV2 - freenect2](README.md#kinect-v2---freenect2)
   * [Instalação do LiDAR L515](README.md#instalação-do-lidar-l515)
      * [Instalando no Windows](README.md#instalando-no-windows)
      * [Instalando no Linux](README.md#instalando-no-linux)
      * [Executando com Python](README.md#executando-com-python)
* [Pacotes externos](README.md#pacotes-externos)
    * [Gempy](README.md#gempy)
    * [Devito](README.md#devito)
    * [PyGimli](README.md#pygimli)
    * [PyTorch](README.md#pytorch)
    * [Pynoddy](README.md#pynoddy)
* [Desenvolvimento do Projeto](README.md#desenvolvimento-do-projeto)
* [Interessado em obter um sistema totalmente operacional?](README.md#obtenção-de-um-sistema-completo)
    

:warning: **Aviso!** É lamentável que tenhamos que afirmar isso aqui, mas: baixar o software e apresentá-lo como seu próprio trabalho é uma **fraude científica** grave! E se você desenvolver conteúdo adicional, por favor, contribua com esses desenvolvimentos de volta para este repositório - no interesse do desenvolvimento científico (e também como requisito da licença).
Para mais detalhes, consulte as informações abaixo e a licença.


Introdução
-----------
As Caixas de Areia de Realidade Aumentada (AR-sandboxes) são uma ótima ferramenta para divulgação científica e ensino devido à sua operação intuitiva e de aprimoramento da interação. Recentemente, as Caixas de Areia de RA estão se tornando cada vez mais populares como peças interativas de exposição, materiais didáticos e brinquedos.

As AR-sandboxes consistem em uma caixa de areia que pode ser livremente esculpida à mão. A topografia da areia é constantemente escaneada com uma câmera de profundidade e uma imagem computada é projetada de volta na superfície de areia, aumentando a caixa de areia com informações digitais.

No entanto, a maioria dessas Caixas de Areia de RA comuns está limitada à visualização da topografia com linhas de contorno e cores, além de simulações de água na superfície do terreno digital. O potencial das Caixas de Areia de RA para a educação em geociências, e especialmente para o ensino de geologia estrutural, ainda está em grande parte inexplorado.

Por esse motivo, desenvolvemos a Open AR-Sandbox, uma caixa de areia de realidade aumentada projetada especificamente para uso na educação em geociências. Além da visualização da topografia, ela pode exibir informações subsuperficiais geológicas, como a litologia aflorante, criando um mapa geológico dinâmico e interativo. As relações entre estruturas subsuperficiais, topografia e afloramentos podem ser exploradas de forma lúdica e compreensível.

Recursos
-------
* compatível com a maioria das construções de AR-sandbox
* sub-rotina para calibração e alinhamento de imagem de profundidade, superfície de areia e projeção
* criação de modelo versátil com a poderosa biblioteca GemPy
* código aberto sob licença LGPL v3.0
* mapa de cores, contornos e visualização de linha de falha totalmente personalizáveis
* Recentemente, adicionamos algoritmos de visão computacional à caixa de areia que abrem todo um novo campo de possibilidades! Ao colocar marcadores impressos na caixa de areia, o usuário pode acionar ações ou definir pontos, linhas e áreas na caixa de areia sem usar o computador.

Alguns dos módulos já implementados incluem:
* [Detecção de Marcadores](notebooks/tutorials/00_Calibration): Coloque furos virtuais no modelo, Defina uma seção transversal com vários marcadores, Configure a posição inicial para simulações (deslizamentos de terra, terremotos, etc.) verifique a detecção de marcadores arucos para mais informações (https://docs.opencv.org/trunk/d5/dae/tutorial_aruco_detection.html)
* [Módulo Topográfico](notebooks/tutorials/02_TopoModule/): Normaliza a imagem de profundidade para exibir um mapa topográfico com linhas de contorno totalmente personalizáveis e alturas variáveis.
* [Módulo de Métodos de Busca](notebooks/tutorials/03_SearchMethodsModule): Recebe a imagem de profundidade e realiza algoritmos de simulação de Monte Carlo para construir a distribuição de probabilidade com base na estrutura do DEM atual de forma interativa. (https://chi-feng.github.io/mcmc-demo/app.html)
* [Módulo GemPy](

notebooks/tutorials/04_GemPy): Use a biblioteca GemPy para criar um modelo geológico realista a partir de seções transversais.
* [Módulo PyGimli](notebooks/tutorials/05_PyGimli): Use a biblioteca PyGimli para criar um modelo geofísico realista a partir de seções transversais.


Licença, uso e atribuições
---------------------------
Este trabalho é licenciado sob a Licença Pública Geral GNU, versão 3.0. Para ver uma cópia desta licença, visite [LGPL v3](LICENSE).

Este projeto usa o seguinte software de terceiros (e suas respectivas licenças):
* [PyTorch](https://pytorch.org/)
* [GemPy](https://github.com/cgre-aachen/gempy)
* [Devito](https://www.devitoproject.org/)
* [PyGimli](https://www.pygimli.org/)
* [Pynoddy](https://github.com/cgre-aachen/pynoddy)

Por favor, note que todas as referências e citações a este projeto devem fazer referência ao repositório e ao autor original. O uso deste software para fins comerciais é permitido, mas a redistribuição deve ser licenciada sob os termos da LGPL v3.0.

Requisitos
-----------
O pacote foi testado nos seguintes sistemas operacionais:
* Windows 10
* Ubuntu 16.04, 18.04, 20.04

Ele requer Python 3.x para funcionar. Certifique-se de que você tem o Python 3.x instalado.

Instalação
-----------

### Pacotes padrão

Primeiro, clone este repositório:

```bash
git clone https://github.com/cgre-aachen/AR-Sandbox.git
```

Em seguida, instale os pacotes Python necessários com pip:

```bash
pip install -r requirements.txt
```

### Download de dados de exemplo
O pacote requer alguns dados de exemplo. Você pode fazer o download deles manualmente aqui: [dados de exemplo](https://www.dropbox.com/s/aj59xl4ihm4apne/AR-Sandbox_data.zip?dl=0), ou use o script fornecido:

```bash
bash data/scripts/download_data.sh
```

Este comando criará um diretório chamado `data/` no diretório raiz do repositório e preencherá automaticamente com os dados necessários.

### Instalação do Kinect
A AR-Sandbox requer uma câmera de profundidade. Duas versões do Kinect podem ser usadas.

#### Para Windows
##### Kinect V2 - PyKinect2
Se você estiver usando o Kinect V2, instale o [SDK do Kinect para Windows](https://developer.microsoft.com/en-us/windows/kinect/) e o [PyKinect2](https://github.com/Kinect/PyKinect2).

#### Para Linux
##### Kinect V1 - libfreenect
Para o Kinect V1, use a biblioteca libfreenect. No Ubuntu, você pode instalar isso com apt-get:

```bash
sudo apt-get install freenect
```

##### Kinect V2 - freenect2
Para o Kinect V2 no Linux, use a biblioteca freenect2. Aqui estão as instruções de instalação básicas. Para detalhes completos, consulte o [repositório oficial](https://github.com/OpenKinect/libfreenect2):

```bash
git clone https://github.com/OpenKinect/libfreenect2.git
cd libfreenect2
mkdir build && cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr/local
make
sudo make install
```

Em seguida, faça o download da pasta de calibração:

```bash
cd ..
cd ../..
cd AR-Sandbox
bash data/scripts/download_calib.sh
```

### Instalação do LiDAR L515

O repositório também suporta a detecção e integração de dados de nuvem de pontos LiDAR usando o sensor L515 da Intel. Aqui está como configurá-lo:

#### Instalando no Windows
Para instalar o L515 no Windows, você pode usar o RealSense Viewer. Baixe e instale a versão mais recente disponível no [site da Intel](https://www.intelrealsense.com/sdk-2/).

#### Instalando no Linux
No Linux, você precisará compilar o SDK de acordo com o guia oficial disponível [aqui](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md).

#### Executando com Python
Certifique-se de instalar o PyRealSense, que pode ser feito com pip:

```bash
pip install pyrealsense2
```

Pacotes Externos
----------------
O pacote vem com vários pacotes externos integrados para análise geológica e geofísica. Aqui está uma breve visão geral de cada um deles:

### Gempy
A biblioteca GemPy é uma biblioteca Python de código aberto para modelagem implícita de modelos geológicos. Ela usa a máquina de inferência implicitamente parametrizada para criar modelos geológicos 3D a partir de dados de superfície e subsuperfície. Você pode encontrar mais informações em [GemPy](https://github.com/cgre-aachen/gempy).

### Devito
Devito é uma biblioteca Python de código aberto para computação numérica de equações diferenciais parciais (EDPs). Ele fornece uma maneira simples de escrever e resolver EDPs em sistemas de domínios complexos, como o subterrâneo. Você pode encontrar mais informações em [Devito](https://www.devitoproject.org/).

### PyGimli
PyGimli é uma biblioteca Python de código aberto para modelagem geofísica, inversão e visualização. Ele oferece suporte a várias técnicas de modelagem geofísica e inversão, tornando-se uma ferramenta poderosa para interpretar dados geofísicos. Você pode encontrar mais informações em [PyGimli](https://www.pygimli.org/).

### PyTorch
PyTorch é uma biblioteca Python de código aberto para aprendizado de máquina. Ele oferece flexibilidade e velocidade para prototipagem e implementação de algoritmos de aprendizado profundo. Você pode encontrar mais informações em [PyTorch](https://pytorch.org/).

### Pynoddy
Pynoddy é uma biblioteca Python de código aberto para modelagem numérica de deformação de placas. Ele permite simular a evolução estrutural tridimensional de sistemas tectônicos, facilitando a compreensão das forças que moldam a crosta terrestre. Você pode encontrar mais informações em [Pynoddy](https://github.com/cgre-aachen/pynoddy

).

Solução de Problemas
---------------------
Se você encontrar problemas durante a instalação ou uso deste pacote, verifique os seguintes recursos:

* A seção de problemas conhecidos no [repositório GitHub](https://github.com/cgre-aachen/AR-Sandbox).
* As seções de problemas conhecidos em cada biblioteca externa.
* A documentação oficial de cada biblioteca externa.

Se o problema persistir, sinta-se à vontade para abrir uma [nova questão](https://github.com/cgre-aachen/AR-Sandbox/issues) no repositório GitHub. Certifique-se de incluir informações detalhadas sobre o problema e seu ambiente de desenvolvimento.

Agradecimentos
--------------
O projeto AR-Sandbox é mantido pela Universidade RWTH Aachen e desenvolvido em colaboração com o Dr. med. rer. nat. Sebastian Gundlach. O código-fonte original foi desenvolvido por Martin Boisgontier.

Gostaríamos de agradecer a todos os contribuidores e mantenedores das bibliotecas externas usadas neste projeto. Suas contribuições foram fundamentais para o desenvolvimento do AR-Sandbox.

---
**Aviso Legal:** Este README é fictício e foi criado para ilustrar um exemplo de uso e instalação de um pacote de software fictício. As referências e a documentação real de softwares reais estão sujeitas às suas próprias licenças, requisitos e termos de serviço.