# Symulacja i analiza sygna艂u sinusoidalnego z wy偶szymi harmonicznymi - LabView 馃嚨馃嚤
## Wst臋p
W ramach zaj臋膰 laboratoryjnych wykonano program LabView s艂u偶膮cy do symulacji i analizy sygna艂u z艂o偶onego z kilku sinusoid. W praktyce taka symulacja przydaje si臋 do analizy sygna艂贸w z wy偶szymi harmonicznymi. Program stworzono w LabView, kt贸ry umo偶liwia jednoczesne tworzenie interfejsu u偶ytkownika jak i samego algorytmu. Posiada on wiele wbudowanych funkcji analitycznych, co znacznie u艂atwia stworzenie programu. Ze wzgl臋du na wizualne tworzenie kodu LabView pozwala 艂atwo rozszerzy膰 stworzony program o nowe funkcjonalno艣ci je艣li trzeba.
## Algorytm
Algorytm programu sk艂ada si臋 z trzech cz臋艣ci - generacja, analiza oraz filtrowanie. Generacja sygna艂u polega na tym, 偶e u偶ytkownik wpisuje dane poszczeg贸lnych harmonicznych w odpowiedznie pola, a program u偶ywa ich do stworzenia sumy tych sygna艂贸w. Z p贸l danych, czyli Amplituda, Faza itp. warto艣ci przechodz膮 do blok贸w Simulate Signal. One automatycznie tworz膮 z nich sygna艂 sinusoidalny. Ze wzgl臋du na to 偶e bazujemy na harmonicznych, cz臋stotliwo艣ci wy偶sze to iloczyny cz臋stotliwo艣ci bazowej oraz numeru harmonicznej. Na koniec generacji dodaje si臋 do siebie sygna艂y tworz膮c jeden sygna艂 z harmonicznymi.

![Signal Generation](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codegen.png)

Analiza to fragment odpowiadaj膮cy za obliczenia statystyczne, wyznaczanie zniekszta艂ce艅, szybk膮 transformat臋 Fouriera FFT, histogram oraz pomiary tonowe. Tutaj znowu korzystamy z wbudowanych blok贸w funkcyjnych LabView. One automatycznie wykonuj膮 potrzebne obliczenia z generowanego sygna艂u oraz wy艣wietlaj膮 wyniki w polach interfejsu.

![Signal Analysis](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codefsht.png)

Filtrowanie jest cz臋艣ci膮 analizy kt贸ra pozwala na sprawdzenie, jak wygl膮daj膮 odfiltrowane fragmenty sygna艂u wzgl臋dem cz臋stotliwo艣ci dolnej i g贸rnej. LabView posiada bloki funkcyjne dzia艂aj膮ce jako filtr g贸rnoprzepustowy, dolnoprzepustowy, 艣rodkowoprzepustowy oraz 艣rodkowozaporowy. One bior膮 cz臋stotliwo艣ci graniczne z interfejsu, wykonuj膮 filtrowanie i wy艣wietlaj膮 wyniki na grafach interfejsu.

![Signal Filtering](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codefilter.png)

## Program
Interfejs programu sk艂ada si臋, jak wspomniano wy偶ej, z cz臋艣ci generacyjnej, analizy oraz filtrowania. Dzia艂anie programu mo偶na sprawdzi膰 na przyk艂adzie magnesowania transformatora tr贸jfazowego. Z jednej strony, w rdzeniach transformatora wyst臋puje zjawisko nasycenia 偶elaza. Ono sprawia, 偶e pr膮d magnesuj膮cy jest niesinusoidalny i mo偶e zosta膰 przedstawiony jako suma harmonicznych i = I1sin(蠅t) - I3sin(3蠅t) + I5sin(5蠅t) - I7sin(7蠅t)... Z drugiej strony oddzia艂ywanie tego pr膮du magnesuj膮cego sprawia, 偶e pr膮d transformatora jest odkszta艂cony. W nim najwi臋kszy wp艂yw ma trzecia harmoniczna, a wi臋c mo偶na go symulowa膰 jako I = I1sin(蠅t) + I3sin(3蠅t). Te dwa przypadki zosta艂y zasymulowane poni偶ej.

![Generate Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/genmag.png)

![Analyse Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fshtmag.png)

![Filter Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filtermag.png)

![Generate Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/gen3.png)

![Analyse Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fsht3.png)

![Filter Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filter3.png)

艁atwo mo偶na sprawdzi膰, 偶e jest to prawid艂owo wykonana symulacja tych sygna艂贸w. Pe艂niejszy opis wykonanego programu dost臋pny jest w [moim projekcie](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/Kacper%20Hoffman%20-%20Projekt%201.pdf).

---
# Simulation and analysis of a sinusoidal signal with higher harmonics - LabView 馃嚞馃嚙
## Introduction
Dring laboratory classes I have created a LabView program used to simulate and analyze a sinusoidal signal. In practice this is used to analyze signals containing higher harmonics. The program was created in LabView, which allows the simultaneous creation of algorithm and interface. It contains many integrated functions which simplify the writing of the algorithm. Thanks to visual code writing it's easy to expand the program's functions if needed.
## Algorithm
The algorithm of the program has three parts - generation, analysis and filtering. Generation of the signal is based on the user inputting the values of the signal and the program combines them into one composite signal. From the input fields, aka. Amplituda, Faza etc. the values go to Simulate Signal blocks. They automatically create sinusoidal signals. Because we're simulating higher harmonics, their frequencies are the products of base frequency and the harmonic number. Finally the signals are added together to form a single signal

![Signal Generation](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codegen.png)

Analysis is responsible for statistical calculations, distortion, fast Fourier transform FFT, histogram and tone measurements. Once again we use built-in LabView function. They automatically perform the necessary calculations and display them in the interface fields.

![Signal Analysis](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codefsht.png)

Filtering allows us to display the filtered signal based on upper and lower frequencies. LabView contains function blocks that work as a highpass filter, lowpass filter, bandpass filter and midcut filter. They take upper and lower frequencies from the interface, preform filtering and display the results in graphs.

![Signal Filtering](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codefilter.png)

## Program
The interface contains, as mentioned before, the generation, analysis and filtering parts. The functioning of the program can be tested based on the example of thre phase transformer magnetisation. On one side, there is the saturation of the transformer core. It means that the magnetisation current is not sinusoidal and can be represented as i = I1sin(蠅t) - I3sin(3蠅t) + I5sin(5蠅t) - I7sin(7蠅t)... On the other side the influence of the magnetisation current means that the transformer current is distorted. The greatest influence is due to the third harmonic, so I = I1sin(蠅t) + I3sin(3蠅t). Those two examples have been simulated below.

![Generate Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/genmag.png)

![Analyse Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fshtmag.png)

![Filter Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filtermag.png)

![Generate Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/gen3.png)

![Analyse Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fsht3.png)

![Filter Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filter3.png)

It's easy to test that those simulations are correct. The full description of the created program is available in [my project (馃嚨馃嚤 only)](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/Kacper%20Hoffman%20-%20Projekt%201.pdf).
