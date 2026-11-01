# Computação Gráfica — OpenGL & FreeGLUT (2026/02)

Repositório público com os materiais teóricos, roteiros de laboratório e códigos-fonte de exemplo da disciplina de **Computação Gráfica**.

---

## Download de Vídeos e Instaladores (Arquivos Grandes)

Para manter a clonagem do repositório leve, os vídeos demonstrativos (`.mp4`) e os instaladores completos para Windows e macOS (JDK, Apache NetBeans, MinGW e GLUT) estão hospedados na aba **Releases** deste repositório:

* **[Clique aqui para acessar a Release v1.0 e baixar os Vídeos e Instaladores](https://github.com/Chiefz2/cg-if-sudeste-2026-02/releases/tag/v1.0)**

---

## Estrutura do Repositório

### Material Teórico e Guias (Raiz)
* **`Computação Gráfica - Apresentação.pdf`**: Ementa, bibliografia e visão geral da disciplina.
* **`Capítulo 01 - Introdução.pdf`**: Fundamentos de Computação Gráfica e sistemas de coordenadas.
* **`Capítulo 02 - Tutorial de instalação.pdf`** e **`Apresentação.pdf`**: Guia passo a passo de configuração do ambiente no Windows e macOS.
* **`Capítulo 03 - Transformações Geométricas - Apresentação.pdf`**: Matrizes de translação, escala, rotação e coordenadas homogêneas.
* **`1º Laboratório.pdf`**: Roteiro prático de exercícios iniciais.

### Códigos Práticos (`Exemplos/`)
* **`_Esqueleto.cpp`**: Estrutura base (template) de um programa OpenGL/GLUT.
* **`_Linker Flags.txt`**: Parâmetros de linkedição para compilar projetos GLUT no Windows.
* **`Ex00.cpp`**: Criação de janela e desenho básico no plano 2D.
* **`Ex01A.cpp` / `Ex01B.cpp` / `Ex01C.cpp`**: Desenho de primitivas geométricas e controle de cores.
* **`Ex02.cpp`**: Manipulação de viewport e projeção ortográfica (`gluOrtho2D`).
* **`Ex03.cpp`**: Interação via eventos e aplicação prática de transformações.

---

## Como Configurar o Ambiente e Compilar

### No Linux (Debian, Ubuntu, Linux Mint, antiX)
Instale o compilador C++ e as bibliotecas de desenvolvimento do FreeGLUT via terminal:
```bash
sudo apt update
sudo apt install build-essential freeglut3-dev libglu1-mesa-dev mesa-common-dev
```
Para compilar e executar qualquer exemplo:
```bash
cd Exemplos/
g++ Ex00.cpp -o Ex00 -lGL -lGLU -lglut
./Ex00
```

### No Windows (MinGW / IDEs C++)
Baixe os instaladores na **[Release v1.0](https://github.com/Chiefz2/cg-if-sudeste-2026-02/releases/tag/v1.0)** e configure as *Linker Flags* conforme o arquivo `Exemplos/_Linker Flags.txt`:
```text
-lfreeglut -lglu32 -lopengl32
```
Para compilar via terminal (MinGW):
```cmd
cd Exemplos
g++ Ex00.cpp -o Ex00.exe -lfreeglut -lglu32 -lopengl32
Ex00.exe
```
