<p align="center">

![FSA](logo/logo_fsa.png)

</p>

<div align="center">
<h1 style="font-weight: bold;">Filtro de Mediana para Imagens em PGM💻</h1>

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

</div>

<div align="center">

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pillow](https://img.shields.io/badge/Pillow-v10.0.4-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-v3.9.2-orange)
![NumPy](https://img.shields.io/badge/NumPy-v2.1.1-lightgrey)

</div>



<p align="center">

  • [Introdução](#introdução-filtro-de-mediana) • [Descrição](#descrição) •  [Funcionalidades](#funcionalidades) • [Instalação](#instalação) • [Como Usar](#como-usar) • [Estrutura do Código](#estrutura-do-código) • [Exemplo de Uso](#exemplo-de-uso) • [Dependências](#dependências) • [Instalação das dependências](#instalação-das-dependências)

</p>


## Introdução Filtro de Mediana

O processamento de imagens é uma área essencial em diversos campos, como medicina, fotografia e visão computacional. Um dos problemas mais comuns no tratamento de imagens é a presença de ruídos, que podem afetar a qualidade visual e a precisão de análises automáticas. 

O filtro de mediana se destaca como uma técnica eficaz para a remoção de ruídos, preservando as bordas e os detalhes das imagens. Diferente de outros filtros de suavização, ele substitui o valor de cada pixel pela mediana dos pixels vizinhos, o que ajuda a minimizar distorções causadas por ruídos impulsivos (como o ruído de "sal e pimenta"). 

Este projeto implementa um filtro de mediana aplicado a imagens no formato PGM, uma maneira simples e eficiente de melhorar a qualidade das imagens sem sacrificar seus detalhes importantes.

## Descrição

Este projeto implementa um filtro de mediana aplicado a imagens no formato PGM (Portable GrayMap). O objetivo é reduzir ruídos presentes nas imagens enquanto preserva os detalhes importantes, como bordas e contornos. Utilizando a biblioteca PIL e funções de processamento em Python, o filtro é capaz de suavizar imagens ruidosas e exibi-las antes e depois do processamento, facilitando a visualização dos resultados.

![Exemplo 1](results/cameraman_filter_size_3.png)

## Funcionamento do Filtro de Mediana

**Tecnica de mediana**: O filtro de mediana é uma técnica amplamente utilizada no processamento de imagens para remover ruídos, como o "ruído sal e pimenta". Ele funciona substituindo o valor de cada pixel da imagem pela mediana dos valores dos seus vizinhos dentro de uma janela de tamanho definido, tipicamente 3x3, 5x5, ou 9x9, sendo o tamanho 9x9 utilizado como padrão no código.

<div align="center">

   ![Professor: Bruno Monserrat Perillo - Fundação Santo André](logo/filtro_sample.png)

</div>

   - **Como funciona no programa**: A imagem é convertida para um array NumPy, que facilita o acesso aos valores dos pixels. Para cada pixel da imagem, uma janela de vizinhança é criada ao redor dele, com o tamanho especificado pelo parâmetro `filter_size`. Os valores de todos os pixels nessa janela são coletados, e a mediana desses valores é calculada e aplicada no pixel central.

   - **Tratamento das bordas**: Quando a janela de vizinhança atinge as bordas da imagem, ela é ajustada automaticamente para considerar apenas os vizinhos dentro dos limites da imagem, evitando erros de acesso a pixels inexistentes.

**Vantagens do filtro de mediana**:

   - **Preservação de detalhes**: Ao contrário de filtros de média ou suavização, o filtro de mediana consegue remover ruídos sem desfocar bordas importantes da imagem.

   - **Eficiência contra ruído sal e pimenta**: Ele é particularmente eficaz contra esse tipo de ruído, que altera os pixels para valores extremos (preto e branco).

## Funcionalidades do Programa

O projeto oferece as seguintes funcionalidades principais:

- **Renderização de Imagens PGM**: Permite carregar e visualizar imagens no formato PGM (Portable GrayMap) ou arrays NumPy representando imagens em escala de cinza.
  
- **Aplicação de Filtro de Mediana**: Aplica um filtro de mediana customizável a imagens, reduzindo ruídos e preservando detalhes importantes, como bordas e contornos. O tamanho da janela do filtro pode ser ajustado para personalizar o nível de suavização.
  
- **Visualização Comparativa**: Exibe lado a lado a imagem original e a imagem filtrada por mediana, facilitando a comparação dos resultados antes e depois do processamento.
  
- **Processamento de Múltiplas Imagens**: Permite o processamento e visualização de várias imagens em um único passo, exibindo todas as imagens originais e filtradas em um layout organizado.
  
- **Compatibilidade com Arrays NumPy**: Além de arquivos PGM, o projeto também suporta imagens carregadas diretamente como arrays NumPy, permitindo flexibilidade no uso.

## Instalação

Para executar este projeto, você precisará instalar algumas bibliotecas em Python. Siga os passos abaixo para configurar o ambiente:

1. Clone o repositório do projeto:
   ```
   git clone https://github.com/KelvenVS/ATV-FM-749422.git
   ```
2. Navegue até o diretório do projeto:
    ```
    cd ATV-FM-749422
    ```
3. Instale as dependências necessárias utilizando o pip:
    - Esses pacotes são utilizados para carregar, processar e exibir as imagens, além de manipular dados durante a execução do filtro de mediana.
    ```
    pip install pillow
    pip install matplotlib
    pip install pandas
    ```
## Como Usar

Após a instalação das dependências e configuração do ambiente, você pode começar a usar o projeto para aplicar o filtro de mediana em imagens. Siga os passos abaixo:

1. **Prepare suas imagens**:
   - Coloque as imagens no formato PGM que deseja processar dentro de uma pasta chamada `pgm` no diretório raiz do projeto.

2. **Execute o script**:
   - Para aplicar o filtro de mediana e visualizar os resultados, basta executar o script principal:
    ```
    python medianFilter.py
    ```

## Estrutura do Código

O projeto está organizado de forma a facilitar o processamento e a visualização de imagens com o filtro de mediana. Abaixo estão descritos os principais componentes do código:

1. **renderPGM(img, axis='on')**:
   - Esta função é responsável por carregar e renderizar uma imagem no formato PGM ou um array NumPy, utilizando a biblioteca Pillow para leitura e o Matplotlib para exibição.
   - Parâmetros:
     - `img`: Caminho do arquivo de imagem ou array NumPy.
     - `axis`: Define se os eixos devem ser exibidos ('on') ou ocultados ('off').

2. **apply_median_filter_1d(image_path, filter_size=9)**:
   - Aplica um filtro de mediana em uma imagem em escala de cinza. O filtro substitui o valor de cada pixel pela mediana de seus vizinhos, suavizando a imagem e removendo ruídos.
   - Parâmetros:
     - `image_path`: Caminho da imagem a ser processada.
     - `filter_size`: Tamanho da janela de vizinhança para o filtro de mediana (valor padrão é 9).

3. **plot_single_image_median_filter(results)**:
   - Plota lado a lado a imagem original e a imagem filtrada por mediana.
   - Parâmetros:
     - `results`: Dicionário contendo as imagens originais, as imagens filtradas e os títulos para exibição.

4. **plot_all_image_median_filter(results, figx=10, figy=10)**:
   - Exibe todas as imagens (originais e filtradas) em um layout de grade. O tamanho da figura pode ser ajustado pelos parâmetros `figx` e `figy`.
   - Parâmetros:
     - `results`: Dicionário com as imagens e títulos.
     - `figx`: Largura da figura em polegadas (padrão 10).
     - `figy`: Altura da figura em polegadas (padrão 10).

5. **process_images_with_median_filter(paramMedian)**:
   - Processa todas as imagens no diretório `pgm`, aplica o filtro de mediana com o tamanho de janela especificado e armazena os resultados (imagens originais e filtradas) em um dicionário.
   - Parâmetros:
     - `paramMedian`: Tamanho da janela de vizinhança para o filtro de mediana.

### Arquivo Principal

- **medianFilter.py**:
   - O arquivo principal do projeto. Ele aplica o filtro de mediana a todas as imagens encontradas na pasta `pgm`, exibindo os resultados através das funções de visualização disponíveis.
   - Pode ser executado diretamente para processar imagens e exibir os resultados.

### Estrutura de Pastas

```
|-- pgm/                # Diretório onde devem ser colocadas as imagens PGM a serem processadas
|-- medianFilter.py  # Arquivo principal contendo as funções e lógica de processamento
```

## Exemplo de Uso

Este exemplo demonstra como usar o projeto para aplicar o filtro de mediana em imagens PGM e visualizar os resultados. 

### Passos:

1. **Adicione suas imagens**: 
   - Coloque os arquivos de imagem no formato PGM dentro do diretório `pgm` que deve estar na raiz do projeto.

2. **Execute o script**:
   - Para processar as imagens com o filtro de mediana e exibir os resultados, execute o seguinte comando no terminal:
   ```
   python medianFilter.py
   ```

3. **Resultados**:
    - O programa aplicará o filtro de mediana a todas as imagens encontradas na pasta `pgm`.
    - Ele exibirá gráficos comparando cada imagem original com a versão filtrada, mostrando as mudanças causadas pelo filtro.
    - Os gráficos serão exibidos de duas formas:
        - Visualização em grade: Todas as imagens originais e filtradas são exibidas em uma única figura, lado a lado.
        - Visualização individual: Para cada par de imagens, uma visualização é exibida separadamente.

**Personalizando o Tamanho do Filtro**

- Se você quiser modificar o tamanho da janela do filtro de mediana, basta alterar o parâmetro na função process_images_with_median_filter dentro do código:
    ```
    imgstratadas = process_images_with_median_filter(5)  # Aplicando filtro de mediana com janela de 5x5
    ```

## Exemplo de Saída
1. Exemplo com imagem única:
    Após a execução, você verá algo assim:

    Imagem Original vs Imagem Filtrada: A imagem original pode conter ruídos (como ruído "sal e pimenta"), e após a aplicação do filtro de mediana, o ruído será reduzido, preservando os detalhes e bordas.
    ![cameraman_filter_size_3](results/cameraman_filter_size_3.png)

2. Exemplo com todas as imagem em um unico arquivo:
    ![all_images](results/all_3x3.png)


## Dependências

Este projeto requer a instalação de algumas bibliotecas Python para funcionar corretamente. Abaixo estão as dependências necessárias:

1. **Pillow (PIL)**:
   - Biblioteca para abrir, manipular e salvar diferentes formatos de imagem. É utilizada para carregar as imagens no formato PGM e convertê-las para escala de cinza.
   - Instalação:
     ```
     pip install pillow
     ```

2. **Matplotlib**:
   - Utilizada para exibir as imagens e gráficos, facilitando a visualização comparativa das imagens originais e filtradas.
   - Instalação:
     ```
     pip install matplotlib
     ```

3. **NumPy**:
   - Necessária para a manipulação de arrays, a NumPy permite que as imagens sejam representadas como matrizes e facilita o processamento dos pixels ao aplicar o filtro de mediana.
   - Instalação:
     ```
     pip install numpy
     ```

## Instalação das dependências
Você pode instalar todas as dependências de uma só vez usando o seguinte comando:

   ```
   pip install pillow matplotlib numpy
   ```

# Desafios

1. **Percorrer e modificar o array NumPy**:
   - **Desafio**: A maior dificuldade foi criar a função que percorresse o array NumPy de forma eficiente, aplicando as modificações do filtro de mediana. Implementar corretamente a lógica de vizinhança e calcular a mediana dos pixels vizinhos foi desafiador, especialmente ao lidar com as bordas da imagem.

   - **Solução**: A solução foi ajustar os loops para que percorrem a imagem garantindo que a janela de vizinhança fosse corretamente definida, especialmente para os pixels nas bordas da imagem. Além disso, utilizei funções nativas do NumPy para facilitar a manipulação dos arrays.

2. **Carregar e manipular imagens PGM com arrays NumPy**:
   - **Desafio**: Carregar as imagens no formato PGM e convertê-las para arrays NumPy, de modo que pudessem ser manipuladas pelos filtros. Além disso, era necessário uma solução que permitisse lidar tanto com arquivos PGM como com imagens já carregadas como arrays NumPy, sem precisar criar funções separadas para cada caso.

   - **Solução**: Para resolver isso, criei uma única função que pudesse lidar tanto com arquivos de imagem PGM quanto com arrays NumPy diretamente. Isso facilitou o processamento das imagens, permitindo maior flexibilidade sem a necessidade de escrever funções diferentes para cada tipo de entrada. Usei a biblioteca Pillow (PIL) para carregar as imagens PGM e convertê-las para escala de cinza quando necessário, e tratei os arrays NumPy diretamente quando fornecidos como entrada.

3. **Trabalhar com o Matplotlib e alinhar gráficos**:
   - **Desafio**: Implementar tanto a visualização das imagens separadamente quanto a exibição de todas as imagens em um único arquivo de visualização. Quando as imagens eram exibidas lado a lado, houve desafios em garantir o alinhamento correto e a organização das imagens para comparação clara entre a imagem original e a imagem filtrada.

   - **Solução**: Para resolver isso, implementei duas funções diferentes. A primeira função lida com a exibição de uma única imagem original e sua versão filtrada, lado a lado, em dois subplots. A segunda função exibe todas as imagens originais e filtradas de uma só vez, organizando-as em uma grade. Para ambas, utilizei a função `plt.tight_layout()` para ajustar automaticamente os subplots e garantir que as imagens fossem exibidas de forma organizada e sem sobreposição.


# Conclusões 

## Comparação dos Resultados com Filtros de Mediana 3x3 e 9x9
Neste projeto, aplicamos o filtro de mediana em imagens PGM utilizando janelas de vizinhança de tamanhos diferentes. Abaixo estão os resultados obtidos com os filtros de 3x3 e 9x9, que ilustram o efeito de suavização do ruído e preservação de detalhes nas imagens processadas.

1. **Filtro de Mediana 3x3**

   ![Cameraman filter size 3](results/cameraman_filter_size_3.png)

   - **Remoção de ruído**: O filtro de tamanho 3x3 foi eficaz em reduzir o ruído do tipo "sal e pimenta" nas imagens. O ruído foi suavizado sem comprometer significativamente os detalhes da imagem, como os contornos do objeto central (o fotógrafo) e as áreas ao redor das bordas.
   - **Preservação de detalhes**: Com uma janela menor (3x3), o filtro conseguiu remover o ruído mantendo a maior parte dos detalhes importantes, como o rosto do fotógrafo e os contornos do tripé. Este filtro é útil quando a remoção de ruído é necessária, mas a preservação dos detalhes finos é uma prioridade.

2. **Filtro de Mediana 9x9**

   ![Cameraman filter size 9](results/cameraman_filter_size_9.png)

   - **Redução de ruído mais agressiva**: Quando utilizamos uma janela maior, como 9x9, o filtro de mediana removeu praticamente todo o ruído da imagem, resultando em uma imagem muito mais limpa e suave.

   - **Perda de detalhes**: No entanto, o uso de um filtro maior também introduziu um borrão perceptível na imagem, afetando a nitidez dos detalhes. Áreas como o rosto do fotógrafo e o tripé perderam definição, e os contornos da imagem ficaram menos precisos. Isso ocorre porque uma janela maior considera mais vizinhos na mediana, resultando em uma suavização mais intensa.

## Conclusão sobre os Filtros 3x3 e 9x9

**Filtro 3x3**: Oferece um equilíbrio entre remoção de ruído e preservação de detalhes. É indicado para situações em que o ruído não é extremo e os detalhes da imagem precisam ser mantidos.

**Filtro 9x9**: Ideal para casos em que o ruído é muito forte e a prioridade é a suavização máxima. No entanto, isso vem com o custo de uma perda maior de detalhes e nitidez nas áreas mais finas da imagem.

- Esses resultados demonstram a importância de escolher o tamanho adequado da janela do filtro de mediana dependendo do tipo de imagem e do nível de ruído presente. Em imagens com muito ruído, o filtro de 9x9 pode ser mais eficaz, mas em imagens onde os detalhes são importantes, o filtro de 3x3 pode oferecer melhores resultados sem comprometer a qualidade visual.


# Filtro 3x3

# Filtro 9x9