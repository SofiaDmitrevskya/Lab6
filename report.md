---
# Front matter
lang: ru-RU
title: "Отчет по ходу лабораторной работы №6"
subtitle: "Модель эпидемии - вариант 19"
author: "Дмитревская Софья Алексеевна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the υalue makes tex try to haυe fewer lines in the paragraph.
  - \interlinepenalty=0 # υalue of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \usepackage{amsmath}
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

## Цель лабораторной работы:
Изучить простейшую модель эпидемии $SIR$. Используя условия из варианты, задать в уравнение начальные условия и коэффициенты.
После построить графики изменения численностей трех групп в двух случаях.

# Задачи
## Задачи лабораторной работы:
1.	Изучить модель эпидемии
2.	Построить графики изменения числа особей в каждой из трех групп. 
3.	Рассмотреть, как будет протекать эпидемия в случае: $I(0)\leq I^*$, $I(0)>I^*$


# Ход выполнения лабораторной работы:

## Теоретические сведения
Рассмотрим простейшую модель эпидемии. Предположим, что некая популяция, состоящая из $N$ особей, (считаем, что популяция изолирована) подразделяется на три группы. Первая группа - это восприимчивые к болезни, но пока здоровые особи, обозначим их через $S(t)$. Вторая группа – это число инфицированных особей, которые также при этом являются распространителями инфекции, обозначим их $I(t)$. А третья группа, обозначающаяся через $R(t)$ – это здоровые особи с иммунитетом к болезни. 
До того, как число заболевших не превышает критического значения $I^*$, считаем, что все больные изолированы и не заражают здоровых. Когда $I(t)> I^*$, тогда инфицирование способны заражать восприимчивых к болезни особей. 

Таким образом, скорость изменения числа $S(t)$ меняется по следующему закону:

$$
\frac{dS}{dt}=
 \begin{cases}
	-\alpha S &\text{,если $I(t) > I^*$}
	\\   
	0 &\text{,если $I(t) \leq I^*$}
 \end{cases}
$$

## Теоретические сведения
Поскольку каждая восприимчивая к болезни особь, которая, в конце концов, заболевает, сама становится инфекционной, то скорость изменения числа инфекционных особей представляет разность за единицу времени между заразившимися и теми, кто уже болеет и лечится. Т.е.:

$$
\frac{dI}{dt}=
 \begin{cases}
	\alpha S -\beta I &\text{,если $I(t) > I^*$}
	\\   
	-\beta I &\text{,если $I(t) \leq I^*$}
 \end{cases}
$$

## Теоретические сведения
Рассмотрим скорость изменения выздоравливающих особей, которые при этом приобретают иммунитет к болезни:

$$\frac{dR}{dt} = \beta I$$

Постоянные пропорциональности $\alpha, \beta$ - это коэффициенты заболеваемости и выздоровления соответственно. Для того, чтобы решения соответствующих уравнений определялось однозначно, необходимо задать начальные условия. Считаем, что на начало эпидемии в момент времени $t=0$ нет особей с иммунитетом к болезни $R(0)=0$, а число инфицированных и восприимчивых к болезни особей $I(0)$ и $S(0)$ соответственно. Для анализа картины протекания эпидемии необходимо рассмотреть два случая:  $I(0) \leq I^*$ и  $I(0)>I^*$

# Задача
## Условие задачи:
На одном небольшом острове вспыхнула эпидемия. 
Известно, что из всех проживающих на острове $(N=10600)$ в момент начала эпидемии $(t=0)$ число заболевших людей (являющихся распространителями инфекции) $I(0)=133$.
Число здоровых людей с иммунитетом к болезни $R(0)=33$. 
Таким образом, число людей восприимчивых к болезни, но пока здоровых, в начальный момент времени $S(0)=N-I(0)-R(0)$.
Постройте графики изменения числа особей в каждой из трех групп.
Рассмотрите, как будет протекать эпидемия в случае:
1.	$I(0)\leq I^*$
2.	$I(0)>I^*$

# Код программы
## Код программы
```
model lab6
parameter Real a = 0.01;// коэффициент заболеваемости
parameter Real b = 0.02;//коэффициент выздоровления
parameter Real N = 10600;// общая численность популяции
parameter Real I0 = 133; // количество инфицированных особей в начальный момент времени
parameter Real R0 = 33; // количество здоровых особей с иммунитетом в начальный момент времени
parameter Real S0 = N - I0 - R0; // количество восприимчивых к болезни особей в начальный момент времени
Real S(start=S0);
Real I(start=I0);
Real R(start=R0);

equation
// случай, когда I(0)<=I*
der(S) = 0;
der(I) = -b*I;
der(R) = b*I;
end lab6;
```

## Код программы
```
model lab62  
  parameter Real a = 0.01;// коэффициент заболеваемости
  parameter Real b = 0.02;//коэффициент выздоровления
  parameter Real N = 10600;// общая численность популяции
  parameter Real I0 = 133; // количество инфицированных особей в начальный момент времени
  parameter Real R0 = 33; // количество здоровых особей с иммунитетом в начальный момент времени
  parameter Real S0 = N - I0 - R0; // количество восприимчивых к болезни особей в начальный момент времени
  Real S(start=S0);
  Real I(start=I0);
  Real R(start=R0);
  
  equation
  
  // случай, когда I(0)> I*
  der(S) = a*S;
  der(I) = a*S - b*I;
  der(R) = b*I;
  
end lab62;
```
# Результаты работы
## Результаты работы
![Графики численности в случае $I(0)\leq I^*$](image/1.jpg){ #fig:001 width=70% height=70% }

![Графики численности в случае $I(0)>I^*$](image/2.jpg){ #fig:002 width=70% height=70% }


# Выводы
В ходе выполнения лабораторной работы была изучена простейшая модель эпидемии и построены графики на основе условий задачи и начальных данных, которые были описаны в варианте лабораторной работы.

# Список литературы {.unnumbered}

1. [Моделирование эпидемии простым языком, SIR модель](https://www.youtube.com/watch?v=ueKT4Mcv-JU)
2. [SIR models of epidemics](https://ethz.ch/content/dam/ethz/special-interest/usys/ibz/theoreticalbiology/education/learningmaterials/701-1424-00L/sir.pdf)
3. [Конструирование эпидемиологических моделей](https://habr.com/ru/post/551682/)