# Computação Gráfica — OpenGL & FreeGLUT (2026/02)

Repositório público com os materiais teóricos, roteiros de laboratório e códigos-fonte de exemplo da disciplina de **Computação Gráfica**. O objetivo deste espaço é facilitar o acesso aos conteúdos e fornecer um guia prático de compilação e estudo para a turma e demais interessados na área.

---

## Estrutura do Repositório

### Material Teórico e Guias (Raiz)
* **`Computação Gráfica - Apresentação.pdf`**: Ementa, bibliografia, critérios de avaliação e visão geral da disciplina.
* **`Capítulo 01 - Introdução.pdf`**: Fundamentos de Computação Gráfica, processamento de imagens, sistemas de coordenadas e aplicações.
* **`Capítulo 02 - Tutorial de instalação.pdf`** e **`Apresentação.pdf`**: Guia passo a passo para configuração do ambiente tradicional no Windows/macOS.
* **`Capítulo 03 - Transformações Geométricas - Apresentação.pdf`**: Matrizes de translação, escala, rotação, cisalhamento e coordenadas homogêneas.
* **`1º Laboratório.pdf`**: Roteiro prático de exercícios iniciais com primitivas gráficas.

### Códigos Práticos (`Exemplos/`)
* **`_Esqueleto.cpp`**: Estrutura base (template) de um programa OpenGL/GLUT contendo a inicialização de janela e funções de *callback* essenciais.
* **`_Linker Flags.txt`**: Parâmetros de *linkedição* necessários para compilar projetos GLUT em IDEs no Windows.
* **`Ex00.cpp`**: Introdução à criação de janela e desenho básico no plano 2D.
* **`Ex01A.cpp` / `Ex01B.cpp` / `Ex01C.cpp`**: Variações práticas de desenho de primitivas geométricas (`GL_POINTS`, `GL_LINES`, `GL_TRIANGLES`, `GL_POLYGON`) e controle de cores (`glColor3f`).
* **`Ex02.cpp`**: Manipulação de *viewport*, projeção ortográfica (`gluOrtho2D`) e estruturação de cena.
* **`Ex03.cpp`**: Interação via eventos de teclado/mouse e aplicação prática de transformações.

---

## Como Configurar o Ambiente (Sem Instaladores Pesados)

Para manter o repositório leve e acessível, os instaladores binários pesados (JDK, NetBeans e vídeos demonstrativos) não estão versionados aqui. Siga as instruções abaixo de acordo com o seu sistema operacional:

### Linux (Debian, Ubuntu, Linux Mint, antiX)
1. Instale o compilador `g++` e as bibliotecas de desenvolvimento do OpenGL e FreeGLUT via terminal:
   ```bash
   sudo apt update
   sudo apt install build-essential freeglut3-dev libglu1-mesa-dev mesa-common-dev
   ```

### Windows (Via MinGW / MSYS2 ou IDEs C++)
1. Caso utilize o guia original da disciplina, consulte o arquivo **`Capítulo 02 - Tutorial de instalação.pdf`**.
2. Em ambientes modernos (VS Code, Code::Blocks ou Dev-C++ com MinGW), instale o pacote **FreeGLUT** e configure as *Linker Flags* conforme o arquivo `Exemplos/_Linker Flags.txt`:
   ```text
   -lfreeglut -lglu32 -lopengl32
   ```

---

## Como Compilar e Executar os Exemplos

### No Terminal Linux
Navegue até a pasta `Exemplos/` e compile qualquer arquivo `.cpp` vinculando as bibliotecas `-lGL`, `-lGLU` e `-lglut`:

```bash
cd Exemplos/
g++ Ex00.cpp -o Ex00 -lGL -lGLU -lglut
./Ex00
```

Para criar um novo exercício a partir do arquivo base:
```bash
cp _Esqueleto.cpp MeuExercicio.cpp
g++ MeuExercicio.cpp -o MeuExercicio -lGL -lGLU -lglut
./MeuExercicio
```

### No Terminal Windows (MinGW)
```cmd
cd Exemplos
g++ Ex00.cpp -o Ex00.exe -lfreeglut -lglu32 -lopengl32
Ex00.exe
```

---

## Roteiro de Estudo Recomendado

1. **Conceitos Base**: Leia o **`Capítulo 01 - Introdução.pdf`** para compreender como o pipeline gráfico mapeia coordenadas do mundo para a tela.
2. **Anatomia do Código**: Abra o arquivo **`Exemplos/_Esqueleto.cpp`** lado a lado com o **`Exemplos/Ex00.cpp`** e identifique o papel das funções `glutInitDisplayMode`, `glutCreateWindow`, `glutDisplayFunc` e `glFlush`.
3. **Prática de Primitivas**: Compile e execute a sequência **`Ex01A.cpp`**, **`Ex01B.cpp`** e **`Ex01C.cpp`**, alterando as coordenadas nos vértices `glVertex2f(x, y)` para observar a mudança imediata na janela gráfica.
4. **Laboratório e Transformações**: Avance para o **`1º Laboratório.pdf`** e o **`Capítulo 03 - Transformações Geométricas - Apresentação.pdf`**, testando os exemplos **`Ex02.cpp`** e **`Ex03.cpp`**.
