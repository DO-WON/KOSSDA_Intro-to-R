# Introduction to R

사람: 익명, 익명
상태: KOSSDA TA

### Note

이 페이지는 KOSSDA 방법론 강좌 수강생들을 위한 R 기초 튜토리얼입니다. 

### Table of Contents

1. **Prerequisites** 
    - **1-1. Installing R RStudio**
        
        [R 설치하기](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%20ba5adfbe9cd2414fb0365b1b9469ecfb.md)
        
    - **1-2. Installing RStudio & R interface**
        
        [R Studio 설치 및 R interface 소개](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20Studio%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20%E1%84%86%E1%85%B5%E1%86%BE%20R%20interface%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2073fc48ab89ee45449d4cbc4ad6046aa6.md)
        
    - **1-3. Creating a Workspace**
        
        [작업 공간(workspace) 만들기](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A9%E1%86%BC%E1%84%80%E1%85%A1%E1%86%AB(workspace)%20%E1%84%86%E1%85%A1%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%80%E1%85%B5%203658928eac0f441c8faf4bdada2971dd.md)
        

---

1. R 기본 문법 **Basic programming in R** 
    - **2-1. Communicating in R language**
        
        [R 문법의 기초](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20%E1%84%86%E1%85%AE%E1%86%AB%E1%84%87%E1%85%A5%E1%86%B8%E1%84%8B%E1%85%B4%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20f3acedcb65b5410788e2311d3935a836.md)
        
    - **2-2. Data type**
        
        [데이터 유형](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%83%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5%20%E1%84%8B%E1%85%B2%E1%84%92%E1%85%A7%E1%86%BC%20ed3c1b5ab34c43349bd5b8e47da67add.md)
        
    - **2-3. Data structure**
        
        [데이터 구조](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%83%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5%20%E1%84%80%E1%85%AE%E1%84%8C%E1%85%A9%20a6aa604b2fd649c89a9adf6e80f2d1e4.md)
        
    - **2-4. R 패키지와 라이브러리 R packages and libraries**
        
        [R 패키지와 라이브러리](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20%E1%84%91%E1%85%A2%E1%84%8F%E1%85%B5%E1%84%8C%E1%85%B5%E1%84%8B%E1%85%AA%20%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%87%E1%85%B3%E1%84%85%E1%85%A5%E1%84%85%E1%85%B5%206ae418c4ccf0461e9e75607deb52e64d.md)
        

---

1. 데이터 다루기 **Data Management** 
    - **3-1. Loading build-in data**
        
        [**내장데이터 불러오기**](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%82%E1%85%A2%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%83%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5%20%E1%84%87%E1%85%AE%E1%86%AF%E1%84%85%E1%85%A5%E1%84%8B%E1%85%A9%E1%84%80%E1%85%B5%204a34fbdab9bf4ce4bd5953343b61ca20.md)
        
    - **3-2. Exporting and importing data**
        
        [데이터 저장하기(내보내기), 불러오기](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%83%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5%20%E1%84%8C%E1%85%A5%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5(%E1%84%82%E1%85%A2%E1%84%87%E1%85%A9%E1%84%82%E1%85%A2%E1%84%80%E1%85%B5),%20%E1%84%87%E1%85%AE%E1%86%AF%E1%84%85%E1%85%A5%E1%84%8B%E1%85%A9%E1%84%80%E1%85%B5%20d793b6ed2fd348969fba96c11dfaa431.md)
        
    - **3-3. Data wrangling & pre-processing: Base functions and Tidyverse**
        
        [데이터 전처리](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%83%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5%20%E1%84%8C%E1%85%A5%E1%86%AB%E1%84%8E%E1%85%A5%E1%84%85%E1%85%B5%20ec4843c19e784e4480b20ba0c9925781.md)
        

---

1. 데이터 시각화 **Visualizastion in R**
    
    먼저 R에서 기본으로 제공하는 base 함수들로 시각화 연습을 해본 후, **`tidyverse`**의 `ggplot2()` 를 통해 시각화하는 연습을 해보겠습니다. 
    
    - **4-1.  R base plot**
        
        [R 기본 그래프](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20%E1%84%80%E1%85%B5%E1%84%87%E1%85%A9%E1%86%AB%20%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%91%E1%85%B3%20774f922b498b4f78846b386fc262ba29.md)
        
    - **4-2. `Tidyverse - ggplot2`**
        
        [`**Tidyverse - ggplot2**`](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Tidyverse%20-%20ggplot2%2086518e9e7c854e42b655e952119acb59.md)
        

---

1. 나가며 **Further Tips**
    - 유용한 소스들 ***Useful open sources***
        
        [Welcome | R for Data Science](https://r4ds.had.co.nz/index.html)
        
        [R Graphics Cookbook, 2nd edition](https://r-graphics.org/)
        
        [Welcome | ggplot2](https://ggplot2-book.org/index.html)