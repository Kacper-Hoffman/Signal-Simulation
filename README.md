# Symulacja i analiza sygnału sinusoidalnego z wyższymi harmonicznymi - LabView 🇵🇱
## Wstęp
W ramach zajęć laboratoryjnych wykonano program LabView służący do symulacji i analizy sygnału złożonego z kilku sinusoid. W praktyce taka symulacja przydaje się do analizy sygnałów z wyższymi harmonicznymi. Program stworzono w LabView, który umożliwia jednoczesne tworzenie interfejsu użytkownika jak i samego algorytmu. Posiada on wiele wbudowanych funkcji analitycznych, co znacznie ułatwia stworzenie programu. Ze względu na wizualne tworzenie kodu LabView pozwala łatwo rozszerzyć stworzony program o nowe funkcjonalności jeśli trzeba.
## Algorytm
Algorytm programu składa się z trzech części - generacja, analiza oraz filtrowanie. Generacja sygnału polega na tym, że użytkownik wpisuje dane poszczególnych harmonicznych w odpowiedznie pola, a program używa ich do stworzenia sumy tych sygnałów. Z pól danych, czyli Amplituda, Faza itp. wartości przechodzą do bloków Simulate Signal. One automatycznie tworzą z nich sygnał sinusoidalny. Ze względu na to że bazujemy na harmonicznych, częstotliwości wyższe to iloczyny częstotliwości bazowej oraz numeru harmonicznej. Na koniec generacji dodaje się do siebie sygnały tworząc jeden sygnał z harmonicznymi.

![Signal Generation](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codegen.png)

Analiza to fragment odpowiadający za obliczenia statystyczne, wyznaczanie zniekształceń, szybką transformatę Fouriera FFT, histogram oraz pomiary tonowe. Tutaj znowu korzystamy z wbudowanych bloków funkcyjnych LabView. One automatycznie wykonują potrzebne obliczenia z generowanego sygnału oraz wyświetlają wyniki w polach interfejsu.

![Signal Analysis](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codefsht.png)

Filtrowanie jest częścią analizy która pozwala na sprawdzenie, jak wyglądają odfiltrowane fragmenty sygnału względem częstotliwości dolnej i górnej. LabView posiada bloki funkcyjne działające jako filtr górnoprzepustowy, dolnoprzepustowy, środkowoprzepustowy oraz środkowozaporowy. One biorą częstotliwości graniczne z interfejsu, wykonują filtrowanie i wyświetlają wyniki na grafach interfejsu.

![Signal Filtering](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/codefilter.png)

## Program
Interfejs programu składa się, jak wspomniano wyżej, z części generacyjnej, analizy oraz filtrowania. Działanie programu można sprawdzić na przykładzie magnesowania transformatora trójfazowego. Z jednej strony, w rdzeniach transformatora występuje zjawisko nasycenia żelaza. Ono sprawia, że prąd magnesujący jest niesinusoidalny i może zostać przedstawiony jako suma harmonicznych i = I1sin(ωt) - I3sin(3ωt) + I5sin(5ωt) - I7sin(7ωt)... Z drugiej strony oddziaływanie tego prądu magnesującego sprawia, że prąd transformatora jest odkształcony. W nim największy wpływ ma trzecia harmoniczna, a więc można go symulować jako I = I1sin(ωt) + I3sin(3ωt). Te dwa przypadki zostały zasymulowane poniżej.

![Generate Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/genmag.png)

![Analyse Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fshtmag.png)

![Filter Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filtermag.png)

![Generate Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/gen3.png)

![Analyse Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fsht3.png)

![Filter Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filter3.png)

Łatwo można sprawdzić, że jest to prawidłowo wykonana symulacja tych sygnałów. Pełniejszy opis wykonanego programu dostępny jest w [moim projekcie](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/Kacper%20Hoffman%20-%20Projekt%201.pdf).

---
# Simulation and analysis of a sinusoidal signal with higher harmonics - LabView 🇬🇧
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
The interface contains, as mentioned before, the generation, analysis and filtering parts. The functioning of the program can be tested based on the example of thre phase transformer magnetisation. On one side, there is the saturation of the transformer core. It means that the magnetisation current is not sinusoidal and can be represented as i = I1sin(ωt) - I3sin(3ωt) + I5sin(5ωt) - I7sin(7ωt)... On the other side the influence of the magnetisation current means that the transformer current is distorted. The greatest influence is due to the third harmonic, so I = I1sin(ωt) + I3sin(3ωt). Those two examples have been simulated below.

![Generate Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/genmag.png)

![Analyse Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fshtmag.png)

![Filter Mag Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filtermag.png)

![Generate Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/gen3.png)

![Analyse Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/fsht3.png)

![Filter Third Signal](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/filter3.png)

It's easy to test that those simulations are correct. The full description of the created program is available in [my project (🇵🇱 only)](https://github.com/Kacper-Hoffman/Signal-Simulation/blob/main/Kacper%20Hoffman%20-%20Projekt%201.pdf).
