---
layout: post
title:  "[python 1] 네이밍 규칙"
author: scjung
categories: [ scjung, python, 기초 ]
image: assets/images/python1/python1-main.png
featured: true
---

<br>
<h2>Background</h2>
코딩을 하는 사람 어느 누구에게 물어도 한 번쯤은 겪어봤을 고민 거리가 있을 것입니다. 어떤 사람은 문제를 해결할 수 없어서, 또 어떤 사람은 최적화가 어려워서 등등이 있겠지만 그보다 더 근본적이고 기초적이지만 한참을 헤매는 고민 거리가 있습니다. 바로 __이름짓기__ 입니다.
변수에 이름을 지을 때 '어떻게 지어야 알아보기 쉽고 꼬이지 않을까' 하는 근본적인 질문부터 '_(언더바)를 써야 돼, 말아야 돼' 하는 사소한 고민까지 존재있을 것입니다.
그래서 이 주제에서는 python에서 자주 쓰는 PEP 부터 개인적으로 쓰는 방식을 서술할 것입니다.

<p align="center" style="margin:0"><img src="/assets/images/python1/python1-1.jpeg"></p>
<p align="center" style="color:gray; font-size: 0.8rem">그림 1. 프로그래머에게 가장 어려운 업무</p>

<br>
<h2>PEP 8</h2>
__PEP__ 는 파이썬에서 공식적으로 권장하는 코드 스타일 가이드입니다.
해당 포스트는 네이밍에 관련된 내용만을 서술하기 때문에 PEP 8 전체에 관련된 궁금한 내용은 [PEP8 가이드](https://www.python.org/dev/peps/pep-0008/) 에서 확인하면 됩니다.

PEP 8에서 소개되는 네이밍 규칙은 아래와 같습니다.

* <p style="font-size:0.9rem; margin:0">b (소문자 1글자)</p>
* <p style="font-size:0.9rem; margin:0">B (대문자 1글자)</p>
* <p style="font-size:0.9rem; margin:0">lowercase (소문자)</p>
* <p style="font-size:0.9rem; margin:0">lower_case_with_underscores (소문자 + 언더바 = snake case / pothole case)</p>
* <p style="font-size:0.9rem; margin:0">UPPERCASE (대문자)</p>
* <p style="font-size:0.9rem; margin:0">UPPER_CASE_WITH_UNDERSCORES (대문자 + 언더바)</p>
* <p style="font-size:0.9rem; margin:0">CapitalizedWords (upper camel case = pascal case)</p>
* <p style="font-size:0.9rem; margin:0">mixedCase (lower camel case)</p>
* <p style="font-size:0.9rem; margin:0">Capitalized_Words_With_Underscores (ugly!)</p>

위 방식들은 네이밍을 할 때 사용할 수 있는 케이스들이며, 이제 여러분들은 위 케이스들을 조합하여 규칙을 만들어야합니다.

<h4>언더 스코어(_) 네이밍 규칙</h4>
아래 규칙은 파이썬에서 사용되는 __언더 스코어 규칙__ 입니다. 위에 소개되었던 케이스들과는 다르게 파이썬에서는 아래 규칙을 __강제__ 하고 있습니다. <br>
(물론 일부는 프로그래머에 따라서 아래 소개되는 방식과 다르게 쓰는 경우도 있습니다. 하지만 해당 규칙을 따르는 것이 협업에 이점을 가져다 줍니다.)

* <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">_single_underbar (_ 앞 1개) : 변수 첫글자가 _ 로 시작되는 경우는 내부적으로 사용되는 변수입니다.</p>
* <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">__double_underbar (_ 앞 2개) : __ 로 시작하는 변수는 class private 속성로 사용됩니다. <br>(class Footbar 내 _boo 라는 변수는 Footbar 내 _Footbar__boo 라는 속성이 됩니다.)</p>
* <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">last_underbar_ (_ 뒤 1개) : 맨 뒤에 언더바 1개가 붙는 경우는 파이썬 내의 다른 키워드와 충돌하지 않기 위한 변수명입니다.</p>
* <p style="font-size:1rem; margin: 0">__magic_method__ (_ 앞 뒤 2개 씩) : 해당 네이밍은 magic method라고 불리며, 클래스 안에 미리 정의되어 있는 사전 예약 함수입니다.</p>

<br>
<h2>변수명 설정</h2>
<p>
프로그래머마다 변수 이름을 짓는 방식이 다른 경우가 많습니다. 물론, 보편적으로 쓰는 변수들도 많고, 한 눈에 알아볼 수 있는 이름들도 있습니다. 하지만, 간혹 특이하게 변수명을 써놔서 알아보기 어려운 (혹은 상상도 못한) 케이스들이 있습니다.<br>
(필자가 정말 특이했다고 느낀 변수명은 협업하는 프로젝트에서 jusoo (주소) 라는 변수명이었습니다.)<br>
</p>
<p>혼자서 모든 코딩을 하는 개인 프로젝트에서 사용하는 변수명들은 본인만 알아봐도 되지만, 여러 사람이서 협업을 하는 프로젝트에서 다른 사람이 알기 어려운 변수명을 사용하는 순간 파국이 일어납니다. 그래서 필자가 여러 경험을 하면서 사용하였던 규칙들을 하나씩 서술하도록 하겠습니다.</p>

<h4>용어 사전 작성</h4>
<p>프로젝트 시작하기 전, 혹은 데이터베이스 테이블을 작성하기 전에 항상 하는 작업들이 있습니다. 그 중 하나는 (당연히!) 용어 사전을 만드는 것입니다.<br>
이전 exerd가 무료일 때는 exerd의 용어 사전을 사용한 후, 데이터 베이스 테이블을 빠르게 만들었지만 지금은 exerd가 유료로 바뀌면서 사용할 수 없게 되었습니다. 대신, 단순하게 엑셀만 가지고 용어 사전을 만들 수 있습니다. <br><br>
용어 사전에 들어가야하는 요소들은 아래와 같습니다.
</p>

* 약어 <span style="font-size:0.8rem">(ex. idx)</span>
* 영어 뜻 <span style="font-size:0.8rem">(ex. index)</span>
* 한글 뜻 <span style="font-size:0.8rem">(ex. 인덱스, 순번)</span>
* 설명 <span style="font-size:0.8rem">(ex. 나열되는 값들의 인덱스)</span>

<p>약어는 변수 이름에 사용되는 글자로 일반적으로는 단어를 줄여서 사용됩니다. 이후의 뜻들과 설명은 해당 약어가 어떤 뜻을 가지는지, 어디서 사용되는지 등에 대해 알아볼 수 있도록 작성합니다. 이외에도 필요하다고 생각되는 요소들을 넣을 수 있지만, 기본적으로 필요한 요소들은 위의 것들이라고 생각됩니다.</p>

<h4>변수 네이밍 규칙</h4>
<p>해당 문단에서는 필자가 자주 쓰는 규칙에 대해서 설명합니다. 해당 내용에 무조건 맞출 필요는 없고, 이런 상황에서는 이렇게 네이밍 규칙을 정하는구나 정도로 인식하시면 되겠습니다.</p>

* <p style="font-size:1rem; margin: 0">변수 : lower_case_with_underscores (snake case)</p>
    * <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">for, if 문 내 지역 변수 : _lower_case_with_underscores (_ + snake case)</p>
* <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">함수 : runCapitalizedWord (lower camel case / 첫 단어는 동사)</p>
* <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">클래스 : CapitalizedWord (pascal case)</p>
* <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">전역 변수 : UPPER_CASE_WITH_UNDERSCORES (대문자 + 언더바)</p>
* <p style="font-size:1rem; margin: 0">파일/폴더 명 : CapitalizedWord.py (pascal case)</p>
    * <p style="font-size:1rem; margin: 0; margin-bottom: 0.5rem">최상위 폴더 명 : lowercase (소문자)</p>

필자가 변수 명을 지을 때는 위의 규칙을 따르면서, 이름만으로 어떤 기능을 하는지, 혹은 어떤 목적으로 쓰이는지를 명확하게 알 수 있는 점도 같이 고려합니다. 이는 __가독성__ 과도 일맥상통합니다. 필자의 생각으로는 코드만 보았을 때 __무슨 기능을 하는 코드다__ 라는 것이 한 눈에 보이도록 하는 것이 중요하다고 생각합니다. (그렇다고 주석을 버리시면 안됩니다 여러분) 그래서 이러한 가독성 측면으로 봤을 때 중요시되어야 하는 것은 아래와 같습니다.

1. 변수 명 만으로 어떤 역할을 하는지 어느 정도 파악이 가능해야 한다.
2. 변수 명이 길어서 가독성을 해치지 말아야 한다. (보통 4~5단어 이내)
3. i, a, b 같은 한 글자 변수는 가급적 지양한다.

<br>
<h2>Foreground</h2>
물론 위 규칙들은 코드를 잘 짜기 위한 여러 요소 중 1가지일 뿐입니다. 위 규칙들을 잘 따른다고 코드가 스파게티가 되버리면 가독성은 결국 개나 줘버리는 상황이 되어버리니 코드도 깔끔하게 짤 수 있는 연습이 필요합니다.

<p align="center" style="margin:0"><img src="/assets/images/python1/python1-2.jpg"></p>
<p align="center" style="color:gray; font-size: 0.8rem">온갖 규칙들을 잘 따르고도 스파게티 코드가 되버리면 IOCCC에 나갈 준비를 해보시는 것도 추천</p>
