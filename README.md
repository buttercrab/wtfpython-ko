> ## 번역
> 번역에 참여하고 싶으시면 [디스코드](https://discord.gg/Xp6QGQ)에 들어오세요!

<p align="center"><img src="/images/logo.png" alt=""></p>
<h1 align="center">What the f*ck Python! 😱</h1>
<p align="center">놀라운 예제들을 통해서 파이썬 탐험하고 이해하기</p>

<p align="center"><a href="https://github.com/satwikkansal/wtfpython">영어 English(원문)</a> | <a href="https://github.com/leisurelicht/wtfpython-cn">중국어 中文</a></p>

다른 읽는 방법: [인터랙티브](https://colab.research.google.com/github/satwikkansal/wtfpython/blob/master/irrelevant/wtf.ipynb) | [CLI](https://pypi.python.org/pypi/wtfpython)

아름답게 디자인되고 고급(high-level)언어이자 인터프리터 언어인 파이썬은 프로그래머의 편의를 위한 기능이 많습니다. 하지만 몇몇 파이썬 예제들의 결과가 한눈에 보기에는 이상할 수 있습니다.

이 문서는 파이썬의 덜 알려지고 비직관적인 예제들이 실제로 어떻게 작동하는지 정확히 설명합니다.

여기에 있는 몇몇 예제들이 WTF까지는 아닐 수도 있지만 잘 모를 수도 있는 파이썬의 흥미로운 부분들이 밝혀집니다. 이러한 예제들이 파이썬의 작동 방식에 대해서 이해하는 것에 대해 좋은 학습 방법이라고 생각합니다.

만약 파이썬의 고인물이라면 예제들을 한 번에 맞춰보세요. 아마 이미 예제들을 접해본 적이 있을 것이고 옛날 추억이 떠오르지 않을까요? :sweat_smile:

추신: 예전에 읽어봤다면 수정사항은 [여기서](https://github.com/satwikkansal/wtfpython/releases/) 확인할 수 있습니다.

추신 2: [옮긴이의 말](https://github.com/buttercrab/wtfpython-ko/blob/3.0/translator.md)을 읽는 것을 추천합니다.

그럼, 시작합니다!

# 목차

<!-- Generated using "markdown-toc -i README.md --maxdepth 3"-->

<!-- toc -->

- [예제의 구성](#예제의-구성)
    + [▶ 빛나는 제목](#-빛나는-제목)
- [사용방법](#사용방법)
- [👀 예제](#-예제)
  * ["머리가 아플수도 있어요!" 단원](#머리가-아플수도-있어요-단원)
    + [▶ 먼저 처음 것들부터 *](#-먼저-처음-것들부터-)
    + [▶ 문자열은 가끔 헷갈려요](#-문자열은-가끔-헷갈려요)
    + [▶ 해시 브라우니](#-해시-브라우니)
    + [▶ 깊이 들어가면 우리는 다 똑같아.](#-깊이-들어가면-우리는-다-똑같아)
    + [▶ 질서 속의 무질서 *](#-질서-속의-무질서-)
    + [▶ 계속 시도해 보세요... *](#-계속-시도해-보세요-)
    + [▶ 무엇을 위해서(for)?](#-무엇을-위해서for)
    + [▶ 실행되는 시간의 차이](#-무엇을-위해서for)
    + [▶ How not to use `is` operator](#-how-not-to-use-is-operator)
    + [▶ `is not ...` is not `is (not ...)`](#-is-not--is-not-is-not-)
    + [▶ A tic-tac-toe where X wins in the first attempt!](#-a-tic-tac-toe-where-x-wins-in-the-first-attempt)
    + [▶ The sticky output function](#-the-sticky-output-function)
    + [▶ The chicken-egg problem *](#-the-chicken-egg-problem-)
    + [▶ Subclass relationships](#-subclass-relationships)
    + [▶ All-true-ation *](#-all-true-ation-)
    + [▶ The surprising comma](#-the-surprising-comma)
    + [▶ Strings and the backslashes](#-strings-and-the-backslashes)
    + [▶ not knot!](#-not-knot)
    + [▶ Half triple-quoted strings](#-half-triple-quoted-strings)
    + [▶ What's wrong with booleans?](#-whats-wrong-with-booleans)
    + [▶ Class attributes and instance attributes](#-class-attributes-and-instance-attributes)
    + [▶ Non-reflexive class method *](#-non-reflexive-class-method-)
    + [▶ yielding None](#-yielding-none)
    + [▶ Yielding from... return! *](#-yielding-from-return-)
    + [▶ Nan-reflexivity *](#-nan-reflexivity-)
    + [▶ Mutating the immutable!](#-mutating-the-immutable)
    + [▶ The disappearing variable from outer scope](#-the-disappearing-variable-from-outer-scope)
    + [▶ The mysterious key type conversion](#-the-mysterious-key-type-conversion)
    + [▶ Let's see if you can guess this?](#-lets-see-if-you-can-guess-this)
  * [Section: Slippery Slopes](#section-slippery-slopes)
    + [▶ Modifying a dictionary while iterating over it](#-modifying-a-dictionary-while-iterating-over-it)
    + [▶ Stubborn `del` operation](#-stubborn-del-operation)
    + [▶ The out of scope variable](#-the-out-of-scope-variable)
    + [▶ Deleting a list item while iterating](#-deleting-a-list-item-while-iterating)
    + [▶ Lossy zip of iterators *](#-lossy-zip-of-iterators-)
    + [▶ Loop variables leaking out!](#-loop-variables-leaking-out)
    + [▶ Beware of default mutable arguments!](#-beware-of-default-mutable-arguments)
    + [▶ Catching the Exceptions](#-catching-the-exceptions)
    + [▶ Same operands, different story!](#-same-operands-different-story)
    + [▶ Be careful with chained operations](#-be-careful-with-chained-operations)
    + [▶ Name resolution ignoring class scope](#-name-resolution-ignoring-class-scope)
    + [▶ Needles in a Haystack *](#-needles-in-a-haystack-)
    + [▶ Splitsies *](#-splitsies-)
    + [▶ Wild imports *](#-wild-imports-)
    + [▶ All sorted? *](#-all-sorted-)
    + [▶ Midnight time doesn't exist?](#-midnight-time-doesnt-exist)
  * [Section: The Hidden treasures!](#section-the-hidden-treasures)
    + [▶ Okay Python, Can you make me fly?](#-okay-python-can-you-make-me-fly)
    + [▶ `goto`, but why?](#-goto-but-why)
    + [▶ Brace yourself!](#-brace-yourself)
    + [▶ Let's meet Friendly Language Uncle For Life](#-lets-meet-friendly-language-uncle-for-life)
    + [▶ Even Python understands that love is complicated](#-even-python-understands-that-love-is-complicated)
    + [▶ Yes, it exists!](#-yes-it-exists)
    + [▶ Ellipsis *](#-ellipsis-)
    + [▶ Inpinity](#-inpinity)
    + [▶ Let's mangle](#-lets-mangle)
  * [Section: Appearances are deceptive!](#section-appearances-are-deceptive)
    + [▶ Skipping lines?](#-skipping-lines)
    + [▶ Teleportation](#-teleportation)
    + [▶ Well, something is fishy...](#-well-something-is-fishy)
  * [Section: Miscellaneous](#section-miscellaneous)
    + [▶ `+=` is faster](#--is-faster)
    + [▶ Let's make a giant string!](#-lets-make-a-giant-string)
    + [▶ Minor Ones *](#-minor-ones-)
- [기여하기](#기여하기)
- [감사의 말](#감사의-말)
- [🎓 License](#-license)
  * [친구들을 놀래켜보세요!](#친구들을-놀래켜보세요)
  * [비슷한 것들을 찾고 있나요?](#비슷한-것들을-찾고-있나요)

<!-- tocstop -->

# 예제의 구성

모든 예제는 아래와 같은 구조로 이루어져 있습니다. 

> ### ▶ 빛나는 제목
>
> ```py
> # 예제 세팅
> # 마법 같은 일을 기대하세요...
> ```
>
> **결과 (유효한 파이썬 버전들):**
>
> ```py
> >>> 입력
> 놀라운 결과
> ```
> 놀라운 결과에 대한 한 줄 설명이 있을 수도 있습니다.
>
>
> #### 💡 설명:
>
> * 무엇이 일어나고 있는지와 왜 일어나는지에 대한 간략한 설명
> ```py
> # 설명을 도울 예제
> ```
> **결과 (유효한 파이썬 버전들):**
>
> ```py
> >>> 입력 # 놀라운 결과의 이해를 돕기 위한 예제
> # 이해 가능한 결과
> ```

**참고:** 여기에 있는 모든 예제는 파이썬 3.5.2 인터렉티브 인터프리터에서 테스트 되었고 추가적으로 명시되어 있지 않은 이상 모든 버전에서 작동할 것입니다. 

# 사용방법

예제들을 순서대로 읽어내려가는 것을 권장하고 예제마다:
- 예제의 코드를 잘 읽어보세요. 만약 파이썬 고인물이라면 대부분 결과가 어떻게 될지 미리 알고 있을 것입니다. 
- 결과를 읽고,
  + 예상한 결과와 실제 결과가 맞는지 확인해 보세요.
  + 결과와 그 작동원리에 대한 정확한 원리를 알고 있나요?
	- 만약 아니라면 (상관없어요), 큰 숨을 한 번 들이마시고, 설명을 읽어보세요 (그래도 이해하지 못했다면, [여기](https://github.com/satwikkansal/wtfPython)에 이슈를 작성해주세요).
	- 알고 있다면, 자신을 한번 토닥여주고 다음 예제로 넘어가세요.

추신: [pypi 패키지](https://pypi.python.org/pypi/wtfpython)를 사용하면 command line에서도 이 문서를 읽을 수 있습니다.
```sh
$ pip install wtfpython -U
$ wtfpython
```
---

# 👀 예제

## "머리가 아플수도 있어요!" 단원

### ▶ 먼저 처음 것들부터 *

<!-- Example ID: d3d73936-3cf1-4632-b5ab-817981338863 -->
<!-- read-only -->

어떤 이유에서인지, 파이썬 3.8의 Walrus 연산자 (`:=`) 가 꽤 알려지게 되었습니다. 확인해봅시다.

1\.

```py
# 파이썬 3.8+

>>> a = "wtf_walrus"
>>> a
'wtf_walrus'

>>> a := "wtf_walrus"
File "<stdin>", line 1
    a := "wtf_walrus"
      ^
SyntaxError: invalid syntax

>>> (a := "wtf_walrus") # 이건 잘 작동하네요
>>> a
'wtf_walrus'
```

2 \.

```py
# 파이썬 3.8+

>>> a = 6, 9
>>> a
(6, 9)

>>> (a := 6, 9)
>>> a
6

>>> a, b = 6, 9 # 전형적인 언패킹
>>> a, b
(6, 9)
>>> (a, b = 16, 19) # 이런
  File "<stdin>", line 1
    (a, b = 6, 9)
          ^
SyntaxError: invalid syntax

>>> (a, b := 16, 19) # 이것은 이상한 3-튜플을 출력합니다.
(6, 16, 19)

>>> a # a가 아직도 안 바뀌었네요?
6

>>> b
16
```



#### 💡 설명

**간단한 walrus 연산자 설명**

walrus 연산자 (`:=`) 는 파이썬 3.8에서 소개되었으며, 변수에 할당하면서 연산을 하고 싶을 때 유용하게 쓰일 수 있습니다. 

```py
def some_func():
		# 많은 계산을 하는 함수라고 가정합시다.
        # time.sleep(1000)
        return 5

# 그래서 
if some_func():
        print(some_func()) # 같은 계산이 두 번 이루어지므로 안 좋은 방법입니다.

# 또는 
a = some_func()
if a:
    print(a)

# 대신에 이렇게 간단하게 쓸 수 있습니다.
if a := some_func():
        print(a)
```

**출력 결과 (> 3.8):**

```py
5
5
5
```

이 연산자는 한 줄의 코드를 아끼고 `some_func`를 두 번 호출하는 것을 방지할 수 있습니다.

- (walrus 연산자를 사용한) 괄호로 묶이지 않은 "할당문(assignment expression)"은 컴파일러의 상위 단계에서 제한되므로 첫 번째 줄 `a := "wtf_walrus"`에서 `SyntaxError`가 발생합니다. 괄호로 묶게 되면 예상했던 대로 작동하고 `a`에 값을 할당하게 됩니다. 

- 정상적으로, `=` 연산자를 포함한 표현식에서는 괄호로 둘러싸는 것이 허용되지 않기 때문에, `(a, b = 6, 9)`에서 syntax error가 발생합니다. 

- walrus 연산자는 `Name`이 유효한 식별자(identifier)이고 `expr`이 유효한 표현식 일 때, `Name := expr`로 사용됩니다. 따라서 패킹과 언패킹은 지원되지 않습니다. 그러므로,

  - `(a := 6, 9)`는 `((a := 6), 9)`와 같고 결국 `(a, 9)` (`a`의 값이 6 일때) 와 같게 됩니다.

    ```py
    >>> (a := 6, 9) == ((a := 6), 9)
    True
    >>> x = (a := 696, 9)
    >>> x
    (696, 9)
    >>> x[0] is a # 둘 다 메모리의 같은 위치를 가리키고 있습니다.
    True
    ```

  - 비슷하게, `(a, b := 16, 19)`는 `(a, (b := 16), 19)`와 같게 되고 이는 단순한 3-튜플과 같습니다.

---

### ▶ 문자열은 가끔 헷갈려요

<!-- Example ID: 30f1d3fc-e267-4b30-84ef-4d9e7091ac1a --->
1\.

```py
>>> a = "some_string"
>>> id(a)
140420665652016
>>> id("some" + "_" + "string") # 두 id가 같네요
140420665652016
```

2\.
```py
>>> a = "wtf"
>>> b = "wtf"
>>> a is b
True

>>> a = "wtf!"
>>> b = "wtf!"
>>> a is b
False

```

3\.

```py
>>> a, b = "wtf!", "wtf!"
>>> a is b # 3.7.x 버전을 제외하고 모든 버전에서 이렇게 작동합니다.
True

>>> a = "wtf!"; b = "wtf!"
>>> a is b # 어디서 실행시키는지에 따라 True 혹은 False가 출력될 것입니다. (파이썬 쉘 / ipython / 파이썬 스크립트)
False
```

```py
# 이번에는 some_file.py 파일에서 실행시켜봅시다.
a = "wtf!"
b = "wtf!"
print(a is b)

# 모듈을 실행시키면 True를 출력하네요.
```

4\.

**출력 결과 (< 3.7 )**

```py
>>> 'a' * 20 is 'aaaaaaaaaaaaaaaaaaaa'
True
>>> 'a' * 21 is 'aaaaaaaaaaaaaaaaaaaaa'
False
```

말이 되는 거 같죠?

#### 💡 설명:
+ 첫 번째와 두 번째 코드에서의 결과는 새로운 객체를 항상 만드는 것보다 이미 존재하고 바뀌지 않는 객체를 사용하려고 하는 CPython 최적화 때문에 그렇습니다. (문자열 interning이라고 부릅니다) 
+ interning이 되고 난 다음, 많은 변수는 같은 메모리에 있는 문자열을 가리키고 있을 겁니다. (메모리를 줄이게 됩니다)
+ 위의 코드들을 보면, 문자열은 알아서 interning이 됩니다. 구현 방식에 따라서 알아서 interning이 될 것인지 결정됩니다. 알아서 interning이 될 것인지 예측해볼 몇 가지 규칙이 있습니다:
  * 길이가 0과 1인 모든 문자열은 interning이 됩니다.
  * 문자열은 컴파일 시간에 interning이 됩니다. (`'wtf'`은 interning이 되지만 `''.join(['w', 't', 'f'])`은 interning이 되지 않습니다)
  * 아스키 문자, 숫자, 언더바 이외의 문자로 이루어져 있으면 interning이 되지 않습니다. 그래서 `'wtf!'`이 `!` 때문에 interning이 되지 않았습니다. CPython에서의 구현은 [여기](https://github.com/python/cpython/blob/3.6/Objects/codeobject.c#L19)서 확인할 수 있습니다.
  ![image](/images/string-intern/string_intern.png)
+ `a`와 `b`가 같은 줄에서 `"wtf!"`의 값으로 할당된다면, 파이썬 인터프리터가 새로운 객체를 만들고 두 번째 변수도 가리키게 만듭니다. 그런데 만약 이 작업을 다른 줄에서 한다면, 파이썬 인터프리터는 이미 `"wtf!"`가 객체로 존재한다는 사실을 모릅니다 (왜냐하면 `"wtf!"`는 interning이 되지 않았기 때문입니다). interning은 컴파일 시간에 작동하는 최적화입니다. 이 최적화는 CPython 3.7.x 버전들에는 적용되지 않았습니다. (더 많은 정보는 이 [이슈](https://github.com/satwikkansal/wtfpython/issues/100)를 확인하세요).
+ IPython과 같은 인터랙티브 환경에서는 하나의 컴파일 유닛(unit)이 하나의 표현식이고 모듈일 때는 모듈 전체일 때도 있습니다. `a, b = "wtf!", "wtf!"`은 하나의 표현식이지만 `a = "wtf!"; b = "wtf!"`은 한 줄에 있는 두 개의 표현식입니다. 그러면 위 예제들의 결과를 설명할 수 있습니다. 
+ 네 번째 출력 결과의 갑작스러운 변화는 [핍홀 최적화](https://en.wikipedia.org/wiki/Peephole_optimization)에 의한 것입니다. 즉 `'a'*20`은 실행 시간에 클록수를 줄이기 위해 컴파일 시간에 `aaaaaaaaaaaaaaaaaaaa`로바뀝니다. 핍홀 최적화는 문자열의 길이가 20 이하일 때만 일어납니다 (`'a'*10**10`의 결과로 `.pyc`파일의 크기를 생각해보세요). [여기](https://github.com/python/cpython/blob/3.6/Python/peephole.c#L288)에 그에 대한 구현이 있습니다. 
+ 참고: 파이썬 3.7에서는 새로운 AST 최적화 새로운 로직으로 핍홀 최적화가 빠졌습니다. 그래서 세 번째 코드가 파이썬 3.7에서는 작동하지 않았습니다. [여기](https://bugs.python.org/issue11549)에서 더 자세히 알아보세요.

---

### ▶ [해시 브라우니](https://ko.wikipedia.org/wiki/%ED%95%B4%EC%8B%9C_%EB%B8%8C%EB%9D%BC%EC%9A%B4%EC%8A%A4)
<!-- Example ID: eb17db53-49fd-4b61-85d6-345c5ca213ff --->
1\.
```py
some_dict = {}
some_dict[5.5] = "JavaScript"
some_dict[5.0] = "Ruby"
some_dict[5] = "Python"
```

**출력 결과:**

```py
>>> some_dict[5.5]
"JavaScript"
>>> some_dict[5.0] # "Python"이 "Ruby"를 사라지게 했네요.
"Python"
>>> some_dict[5] 
"Python"

>>> complex_five = 5 + 0j
>>> type(complex_five)
complex
>>> some_dict[complex_five]
"Python"
```

그래서, 왜 파이썬이 여기저기서 발견되나요?


#### 💡 설명

* 파이썬 딕셔너리(dictionary)는 두 키가 같은지 판별하기 위해 해시값을 사용합니다. 
* 파이썬에서 같은 값을 같는 고정된 객체는 항상 같은 해시값을 가집니다.
  ```py
  >>> 5 == 5.0 == 5 + 0j
  True
  >>> hash(5) == hash(5.0) == hash(5 + 0j)
  True
  ```
  **참고:** 다른 값을 가지고 있는 객체도 같은 해시값을 가질 수 있습니다. ([해시 충돌](https://ko.wikipedia.org/wiki/%ED%95%B4%EC%8B%9C_%EC%B6%A9%EB%8F%8C)이라고 알려져 있습니다)
* `some_dict[5] = "Python"`이 실행되면, 파이썬은 `5`와 `5.0`을 같은 키로 인식하므로 기존 값인 "Ruby"가 "Python"로 덮여 쓰입니다. 
* 이 스택 오버플로우 [답변](https://stackoverflow.com/a/32211042/4354153)이 이유를 설명합니다.

---

### ▶ 깊이 들어가면 우리는 다 똑같아.
<!-- Example ID: 8f99a35f-1736-43e2-920d-3b78ec35da9b --->
```py
class WTF:
  pass
```

**출력 결과:**
```py
>>> WTF() == WTF() # 두 인스턴스는 같을 수 없습니다
False
>>> WTF() is WTF() # 메모리 위에서도 다르네요
False
>>> hash(WTF()) == hash(WTF()) # 해시는 _당연히_ 같아야 합니다
True
>>> id(WTF()) == id(WTF())
True
```

#### 💡 설명:

* `id`가 호출되었을 때, 파이썬에서 `WTF` 객체를 만들고 `id` 함수로 넘겨줍니다. `id` 함수는 그 객체의 아이디(`id`, 메모리상의 위치)를 가져오고 객체를 버립니다. 객체는 파괴됩니다.
* 만약 이것을 두 번 한다면, 파이썬은 두 번째 객체도 같은 메모리에 할당하게 됩니다. (CPython에서는) `id`가 메모리의 위치를 객체의 아이디로 쓰기 때문에 두 아이디는 같게 됩니다.
* 그래서 객체의 아이디는 객체가 파괴되지 않는 한 고유합니다. 객체가 파괴된 후 또는 생성되기 이전에는 다른 것이 같은 아이디를 가질 수도 있습니다.
* 그러면 왜 `is` 연산자는 `False`라고 출력했을까요? 이 코드를 보세요.
  ```py
  class WTF(object):
    def __init__(self): print("I")
    def __del__(self): print("D")
  ```

  **출력 결과:**
  ```py
  >>> WTF() is WTF()
  I
  I
  D
  D
  False
  >>> id(WTF()) == id(WTF())
  I
  D
  I
  D
  True
  ```
  여러분도 보셨다시피 객체들이 만들어지고 파괴되는 순서가 다르게 됩니다.

---

### ▶ 질서 속의 무질서 *
<!-- Example ID: 91bff1f8-541d-455a-9de4-6cd8ff00ea66 --->
```py
from collections import OrderedDict

dictionary = dict()
dictionary[1] = 'a'; dictionary[2] = 'b';

ordered_dict = OrderedDict()
ordered_dict[1] = 'a'; ordered_dict[2] = 'b';

another_ordered_dict = OrderedDict()
another_ordered_dict[2] = 'b'; another_ordered_dict[1] = 'a';

class DictWithHash(dict):
    """
	__hash__ 마법을 구현하는 dict
    """
    __hash__ = lambda self: 0

class OrderedDictWithHash(OrderedDict):
    """
	__hash__ 마법을 구현하는 OrderedDict
    """
    __hash__ = lambda self: 0
```

**출력 결과**
```py
>>> dictionary == ordered_dict # 만약 a == b 이고,
True
>>> dictionary == another_ordered_dict # b == c 이면
True
>>> ordered_dict == another_ordered_dict # 왜 c == a 가 아닐까요?
False

# 집합(set)은 유일한 원소들만 가지고 있으므로,
# 위의 딕셔너리로 집합을 만들고 어떤 일이 일어나는지 알아봅시다.

>>> len({dictionary, ordered_dict, another_ordered_dict})
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'dict'

# 딕셔너리는 __hash__가 구현되어있지 않으므로 그런것 같네요. 
# 그러면 위에서 만든 래퍼(wrapper) 클래스를 써봅시다.
>>> dictionary = DictWithHash()
>>> dictionary[1] = 'a'; dictionary[2] = 'b';
>>> ordered_dict = OrderedDictWithHash()
>>> ordered_dict[1] = 'a'; ordered_dict[2] = 'b';
>>> another_ordered_dict = OrderedDictWithHash()
>>> another_ordered_dict[2] = 'b'; another_ordered_dict[1] = 'a';
>>> len({dictionary, ordered_dict, another_ordered_dict})
1
>>> len({ordered_dict, another_ordered_dict, dictionary}) # 순서를 바꿔봅시다.
2
```

무슨 일이 벌어지고 있는거죠?

#### 💡 설명:

- `dictionary` 그리고 `ordered_dict`, `another_ordered_dict`가 자동적으로 같지 않은 이유는 `OrderedDict` 클래스에서 `__eq__` 메소드가 구현된 방식 때문입니다. [도큐먼트](https://docs.python.org/3/library/collections.html#ordereddict-objects)에서 
	> OrderedDict 오브젝트이 같음을 확인하는 방법은 순서와 관련이 있고 `list(od1.items())==list(od2.items())`로 구현되어 있습니다. `OrderedDict` 오프젝트와 다른 매핑 오프젝트들의 같음을 확인하는 방법은 순서와 상관있습니다.
- 위와 같이 동작하는 이유는 `OrderedDict` 오브젝트가 바로 보통의 딕셔너리가 사용되는 곳에 사용될 수 있게 하기 위해서 입니다. 
- 그러면 왜 `set` 오브젝트에서 순서를 바꾼것이 왜 길이에 영향을 미친 것일까요? 같음을 확인하는 함수가 잘 구현되어 있지 않기 때문입니다. 집합(set)은 유일한 원소들의 순서를 고려하지 않은 자료구조이므로, 각 원소를 삽입하는 순서는 상관이 없어야 합니다. 하지만 이 경우에는 상관이 있네요. 한번 깊이 들어가 봅시다.
    ```py
    >>> some_set = set()
    >>> some_set.add(dictionary) # 이것들은 위의 코드에서의 매핑 오브젝트들입니다
    >>> ordered_dict in some_set
    True
    >>> some_set.add(ordered_dict)
    >>> len(some_set)
    1
    >>> another_ordered_dict in some_set
    True
    >>> some_set.add(another_ordered_dict)
    >>> len(some_set)
    1

    >>> another_set = set()
    >>> another_set.add(ordered_dict)
    >>> another_ordered_dict in another_set
    False
    >>> another_set.add(another_ordered_dict)
    >>> len(another_set)
    2
    >>> dictionary in another_set
    True
    >>> another_set.add(another_ordered_dict)
    >>> len(another_set)
    2
    ```
	그래서 `ordered_dict == another_ordered_dict`이 `False`이고 `ordered_dict`이 `another_set`안에 들어있었으므로 `another_ordered_dict in another_set`이 `False`인 모순으로 인해서 생긴일 입니다.

---

### ▶ 계속 시도해 보세요... *
<!-- Example ID: b4349443-e89f-4d25-a109-82616be9d41a --->
```py
def some_func():
    try:
        return 'from_try'
    finally:
        return 'from_finally'

def another_func(): 
    for _ in range(3):
        try:
            continue
        finally:
            print("Finally!")

def one_more_func(): # 알았다!
    try:
        for i in range(3):
            try:
                1 / i
            except ZeroDivisionError:
				# 여기서 에러를 발생시키고 반복문 밖에서 다뤄보도록 하죠
                raise ZeroDivisionError("A trivial divide by zero error")
            finally:
                print("Iteration", i)
                break
    except ZeroDivisionError as e:
        print("Zero division error ocurred", e)
```

**출력 결과:**

```py
>>> some_func()
'from_finally'

>>> another_func()
Finally!
Finally!
Finally!

>>> 1 / 0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero

>>> one_more_func()
Iteration 0

```

#### 💡 설명:

- `return` 또는 `break`, `continue`가 "try-finally" 에서의 `try`문 안에서 실행된다면, `finally` 구문도 끝나기 전에 실행됩니다.
- 함수의 리턴값은 마지막 리턴문에 의해 결정됩니다. `finally` 구문이 항상 마지막에 실행되므로, `finally` 안에 있는 리턴문이 실행됩니다.
- 여기서 주의할 점은 만약 `finally` 구문 안에서 `return`이나 `break`이 있을 때 임시로 저장된 예외가 없어집니다.

---


### ▶ 무엇을 위해서(for)?
<!-- Example ID: 64a9dccf-5083-4bc9-98aa-8aeecde4f210 --->
```py
some_string = "wtf"
some_dict = {}
for i, some_dict[i] in enumerate(some_string):
    i = 10
```

**출력결과:**
```py
>>> some_dict # 딕셔너리가 나타나네요
{0: 'w', 1: 't', 2: 'f'}
```

####  💡 설명:

* `for` 문은 [파이썬 문법](https://docs.python.org/3/reference/grammar.html)에서 정의되어 있습니다:
  ```
  for_stmt: 'for' exprlist 'in' testlist ':' suite ['else' ':' suite]
  ```
  `exprlist`는 할당되는 부분입니다. 이는 `{exprlist} = {next_value}`와 같다는 말이고 **각각의 원소에 대해 실행됩니다.** 
  아래에 재미있는 예제가 있습니다.
  ```py
  for i in range(4):
      print(i)
      i = 10
  ```

  **출력 결과:**
  ```
  0
  1
  2
  3
  ```

  반복문이 한 번만 돌기를 기대했나요?

  **💡 설명:**

  - 반복문이 파이썬에서 특별하게 작동하기 때문에 할당문 `i = 10`은 절대로 반복문에 영향을 끼치지 않습니다. 매번 반복하기 전에 반복자(iterator)에 의해 제공된 값(위 경우는 `range(4)`)들이 변수(위 경우는 `i`)에 할당됩니다. 

* `enumerate(some_string)` 함수는 반복마다 새로운 값 `i` (하나씩 올라가는 카운터)와 `some_string`에 있는 문자 하나씩을 yield 합니다. 그리고 딕셔너리 `some_dict`에 키가 `i`인 값을 그 문자로 지정합니다. 반복문을 풀어보면 아래처럼 나올 수 있습니다:
  ```py
  >>> i, some_dict[i] = (0, 'w')
  >>> i, some_dict[i] = (1, 't')
  >>> i, some_dict[i] = (2, 'f')
  >>> some_dict
  ```

---

### ▶ 실행되는 시간의 차이
<!-- Example ID: 6aa11a4b-4cf1-467a-b43a-810731517e98 --->
1\.
```py
array = [1, 8, 15]
# 전형적인 제너레이터(generator) 예제입니다
gen = (x for x in array if array.count(x) > 0)
array = [2, 8, 22]
```

**출력 결과:**

```py
>>> print(list(gen)) # 다른 값들은 어디 갔나요?
[8]
```

2\.

```py
array_1 = [1,2,3,4]
gen_1 = (x for x in array_1)
array_1 = [1,2,3,4,5]

array_2 = [1,2,3,4]
gen_2 = (x for x in array_2)
array_2[:] = [1,2,3,4,5]
```

**출력 결과:**
```py
>>> print(list(gen_1))
[1, 2, 3, 4]

>>> print(list(gen_2))
[1, 2, 3, 4, 5]
```

3\.

```py
array_3 = [1, 2, 3]
array_4 = [10, 20, 30]
gen = (i + j for i in array_3 for j in array_4)

array_3 = [4, 5, 6]
array_4 = [400, 500, 600]
```

**출력 결과:**
```py
>>> print(list(gen))
[401, 501, 601, 402, 502, 602, 403, 503, 603]
```

#### 💡 설명

- [제너레이터](https://wiki.python.org/moin/Generators)에서는 `in` 부분은 선언할 때 실행되지만 조건문은 런타임에 실행됩니다. 
- 그래서 런타임 이전에, `array`가 `[2, 8, 22]`로 재할당 되고 `1`, `8`, `15`중에 `8`이 개수가 `0`보다 크므로 제너레이터는 오직 `8`만 yield 합니다.
- 두 번쨰 예제의 `gen_1`과 `gen_2`의 출력 결과가 다른 이유는 `array_1`과 `array_2`가 재할당되는 방법이 다르기 때문입니다.
- 첫 번째 경우에는, `array_1`이 새로운 객체인 `[1, 2, 3, 4, 5]`가 할당되고 `in` 부분은 선언할 때 계산되기 때문에 계속 이전 객체인 `[1, 2, 3, 4]`를 가지고 있습니다.
- 두 번째 경우에는, `array_2`에 슬라이스 객체가 할당될 때 이전의 객체인 `[1, 2, 3, 4]`를 `[1, 2, 3, 4, 5]`로 변화시킵니다. 따라서 `g2`와 `array_2` 모두 같은 (새롭게 `[1, 2, 3, 4, 5]`로 업데이트된) 객체를 가리키고 있습니다. 
- 좋아요, 그런데 지금까지의 로직을 살펴보면, 세 번째 예제의 `list(g)`의 값이 `[11, 21, 31, 12, 22, 32, 13, 23, 33]` 가 되어야 하는 것이 아닌가요? (왜냐하면 `array_3`과 `array_4`가 `array_1`처럼 행동할 테니까요). (오직) `array_4`의 값만이 업데이트되는 이유는 [PEP-289](https://www.python.org/dev/peps/pep-0289/#the-details)에서 설명되어 있습니다
  
    > for 구문의 가장 바깥쪽 부분만 바로 계산되고, 다른 구문들은 제너레이터가 실행될때까지 참조되는 것이 없습니다.

---

### ▶ How not to use `is` operator
<!-- Example ID: 230fa2ac-ab36-4ad1-b675-5f5a1c1a6217 --->
The following is a very famous example present all over the internet.

1\.

```py
>>> a = 256
>>> b = 256
>>> a is b
True

>>> a = 257
>>> b = 257
>>> a is b
False
```

2\.

```py
>>> a = []
>>> b = []
>>> a is b
False

>>> a = tuple()
>>> b = tuple()
>>> a is b
True
```

3\.
**Output**

```py
>>> a, b = 257, 257
>>> a is b
True
```

**Output (Python 3.7.x specifically)**

```py
>>> a, b = 257, 257
>> a is b
False
```

#### 💡 Explanation:

**The difference between `is` and `==`**

* `is` operator checks if both the operands refer to the same object (i.e., it checks if the identity of the operands matches or not).
* `==` operator compares the values of both the operands and checks if they are the same.
* So `is` is for reference equality and `==` is for value equality. An example to clear things up,
  ```py
  >>> class A: pass
  >>> A() is A() # These are two empty objects at two different memory locations.
  False
  ```

**`256` is an existing object but `257` isn't**

When you start up python the numbers from `-5` to `256` will be allocated. These numbers are used a lot, so it makes sense just to have them ready.

Quoting from https://docs.python.org/3/c-api/long.html
> The current implementation keeps an array of integer objects for all integers between -5 and 256, when you create an int in that range you just get back a reference to the existing object. So it should be possible to change the value of 1. I suspect the behavior of Python, in this case, is undefined. :-)

```py
>>> id(256)
10922528
>>> a = 256
>>> b = 256
>>> id(a)
10922528
>>> id(b)
10922528
>>> id(257)
140084850247312
>>> x = 257
>>> y = 257
>>> id(x)
140084850247440
>>> id(y)
140084850247344
```

Here the interpreter isn't smart enough while executing `y = 257` to recognize that we've already created an integer of the value `257,` and so it goes on to create another object in the memory.

Similar optimization applies to other **immutable** objects like empty tuples as well. Since lists are mutable, that's why `[] is []` will return `False` and `() is ()` will return `True`. This explains our second snippet. Let's move on to the third one, 

**Both `a` and `b` refer to the same object when initialized with same value in the same line.**

**Output**

```py
>>> a, b = 257, 257
>>> id(a)
140640774013296
>>> id(b)
140640774013296
>>> a = 257
>>> b = 257
>>> id(a)
140640774013392
>>> id(b)
140640774013488
```

* When a and b are set to `257` in the same line, the Python interpreter creates a new object, then references the second variable at the same time. If you do it on separate lines, it doesn't "know" that there's already `257` as an object.

* It's a compiler optimization and specifically applies to the interactive environment. When you enter two lines in a live interpreter, they're compiled separately, therefore optimized separately. If you were to try this example in a `.py` file, you would not see the same behavior, because the file is compiled all at once. This optimization is not limited to integers, it works for other immutable data types like strings (check the "Strings are tricky example") and floats as well,

  ```py
  >>> a, b = 257.0, 257.0
  >>> a is b
  True
  ```

* Why didn't this work for Python 3.7? The abstract reason is because such compiler optimizations are implementation specific (i.e. may change with version, OS, etc). I'm still figuring out what exact implementation change cause the issue, you can check out this [issue](https://github.com/satwikkansal/wtfpython/issues/100) for updates.

---

### ▶ `is not ...` is not `is (not ...)`
<!-- Example ID: b26fb1ed-0c7d-4b9c-8c6d-94a58a055c0d --->
```py
>>> 'something' is not None
True
>>> 'something' is (not None)
False
```

#### 💡 Explanation

- `is not` is a single binary operator, and has behavior different than using `is` and `not` separated.
- `is not` evaluates to `False` if the variables on either side of the operator point to the same object and `True` otherwise.

---

### ▶ A tic-tac-toe where X wins in the first attempt!
<!-- Example ID: 69329249-bdcb-424f-bd09-cca2e6705a7a --->

```py
# Let's initialize a row
row = [""] * 3 #row i['', '', '']
# Let's make a board
board = [row] * 3
```

**Output:**

```py
>>> board
[['', '', ''], ['', '', ''], ['', '', '']]
>>> board[0]
['', '', '']
>>> board[0][0]
''
>>> board[0][0] = "X"
>>> board
[['X', '', ''], ['X', '', ''], ['X', '', '']]
```

We didn't assign three `"X"`s, did we?

#### 💡 Explanation:

When we initialize `row` variable, this visualization explains what happens in the memory

![image](/images/tic-tac-toe/after_row_initialized.png)

And when the `board` is initialized by multiplying the `row`, this is what happens inside the memory (each of the elements `board[0]`, `board[1]` and `board[2]` is a reference to the same list referred by `row`)

![image](/images/tic-tac-toe/after_board_initialized.png)

We can avoid this scenario here by not using `row` variable to generate `board`. (Asked in [this](https://github.com/satwikkansal/wtfpython/issues/68) issue).

```py
>>> board = [['']*3 for _ in range(3)]
>>> board[0][0] = "X"
>>> board
[['X', '', ''], ['', '', ''], ['', '', '']]
```

---

### ▶ The sticky output function
<!-- Example ID: 4dc42f77-94cb-4eb5-a120-8203d3ed7604 --->

1\.

```py
funcs = []
results = []
for x in range(7):
    def some_func():
        return x
    funcs.append(some_func)
    results.append(some_func())  # note the function call here

funcs_results = [func() for func in funcs]
```

**Output:**

```py
>>> results
[0, 1, 2, 3, 4, 5, 6]
>>> funcs_results
[6, 6, 6, 6, 6, 6, 6]
```
Even when the values of `x` were different in every iteration prior to appending `some_func` to `funcs`, all the functions return 6.

2\.

```py
>>> powers_of_x = [lambda x: x**i for i in range(10)]
>>> [f(2) for f in powers_of_x]
[512, 512, 512, 512, 512, 512, 512, 512, 512, 512]
```

#### 💡 Explanation

- When defining a function inside a loop that uses the loop variable in its body, the loop function's closure is bound to the variable, not its value. So all of the functions use the latest value assigned to the variable for computation.

- To get the desired behavior you can pass in the loop variable as a named variable to the function. **Why this works?** Because this will define the variable again within the function's scope.

    ```py
    funcs = []
    for x in range(7):
        def some_func(x=x):
            return x
        funcs.append(some_func)
    ```

    **Output:**
    ```py
    >>> funcs_results = [func() for func in funcs]
    >>> funcs_results
    [0, 1, 2, 3, 4, 5, 6]
    ```

---

### ▶ The chicken-egg problem *
<!-- Example ID: 60730dc2-0d79-4416-8568-2a63323b3ce8 --->
1\.
```py
>>> isinstance(3, int)
True
>>> isinstance(type, object)
True
>>> isinstance(object, type)
True
```

So which is the "ultimate" base class? There's more to the confusion by the way,

2\. 

```py
>>> class A: pass
>>> isinstance(A, A)
False
>>> isinstance(type, type)
True
>>> isinstance(object, object)
True
```

3\.

```py
>>> issubclass(int, object)
True
>>> issubclass(type, object)
True
>>> issubclass(object, type)
False
```


#### 💡 Explanation

- `type` is a [metaclass](https://realpython.com/python-metaclasses/) in Python.
- **Everything** is an `object` in Python, which includes classes as well as their objects (instances).
- class `type` is the metaclass of class `object`, and every class (including `type`) has inherited directly or indirectly from `object`.
- There is no real base class among `object` and `type`. The confusion in the above snippets is arising because we're thinking about these relationships (`issubclass` and `isinstance`) in terms of Python classes. The relationship between `object` and `type` can't be reproduced in pure python. To be more precise the following relationships can't be reproduced in pure Python,
    + class A is an instance of class B, and class B is an instance of class A.
    + class A is an instance of itself.
- These relationships between `object` and `type` (both being instances of each other as well as themselves) exist in Python because of "cheating" at the implementation level.

---

### ▶ Subclass relationships
<!-- Example ID: 9f6d8cf0-e1b5-42d0-84a0-4cfab25a0bc0 --->
**Output:**
```py
>>> from collections import Hashable
>>> issubclass(list, object)
True
>>> issubclass(object, Hashable)
True
>>> issubclass(list, Hashable)
False
```

The Subclass relationships were expected to be transitive, right? (i.e., if `A` is a subclass of `B`, and `B` is a subclass of `C`, the `A` _should_ a subclass of `C`)

#### 💡 Explanation:

* Subclass relationships are not necessarily transitive in Python. Anyone is allowed to define their own, arbitrary `__subclasscheck__` in a metaclass.
* When `issubclass(cls, Hashable)` is called, it simply looks for non-Falsey "`__hash__`" method in `cls` or anything it inherits from.
* Since `object` is hashable, but `list` is non-hashable, it breaks the transitivity relation.
* More detailed explanation can be found [here](https://www.naftaliharris.com/blog/python-subclass-intransitivity/).

---

### ▶ All-true-ation *

<!-- Example ID: dfe6d845-e452-48fe-a2da-0ed3869a8042 -->

```py
>>> all([True, True, True])
True
>>> all([True, True, False])
False

>>> all([])
True
>>> all([[]])
False
>>> all([[[]]])
True
```

Why's this True-False alteration?

#### 💡 Explanation:

- The implementation of `all` function is equivalent to

- ```py
  def all(iterable):
      for element in iterable:
          if not element:
              return False
      return True
  ```

- `all([])` returns `True` since the iterable is empty. 
- `all([[]])` returns `False` because `not []` is `True` is equivalent to `not False` as the list inside the iterable is empty.
- `all([[[]]])` and higher recursive variants are always `True` since `not [[]]`, `not [[[]]]`, and so on are equivalent to `not True`.

---

### ▶ The surprising comma
<!-- Example ID: 31a819c8-ed73-4dcc-84eb-91bedbb51e58 --->
**Output (< 3.6):**

```py
>>> def f(x, y,):
...     print(x, y)
...
>>> def g(x=4, y=5,):
...     print(x, y)
...
>>> def h(x, **kwargs,):
  File "<stdin>", line 1
    def h(x, **kwargs,):
                     ^
SyntaxError: invalid syntax

>>> def h(*args,):
  File "<stdin>", line 1
    def h(*args,):
                ^
SyntaxError: invalid syntax
```

#### 💡 Explanation:

- Trailing comma is not always legal in formal parameters list of a Python function.
-  In Python, the argument list is defined partially with leading commas and partially with trailing commas. This conflict causes situations where a comma is trapped in the middle, and no rule accepts it.
-  **Note:** The trailing comma problem is [fixed in Python 3.6](https://bugs.python.org/issue9232). The remarks in [this](https://bugs.python.org/issue9232#msg248399) post discuss in brief different usages of trailing commas in Python.

---

### ▶ Strings and the backslashes
<!-- Example ID: 6ae622c3-6d99-4041-9b33-507bd1a4407b --->
**Output:**
```py
>>> print("\"")
"

>>> print(r"\"")
\"

>>> print(r"\")
File "<stdin>", line 1
    print(r"\")
              ^
SyntaxError: EOL while scanning string literal

>>> r'\'' == "\\'"
True
```

#### 💡 Explanation

- In a usual python string, the backslash is used to escape characters that may have a special meaning (like single-quote, double-quote, and the backslash itself).
    ```py
    >>> 'wt\"f'
    'wt"f'
    ```
- In a raw string literal (as indicated by the prefix `r`),  the backslashes pass themselves as is along with the behavior of escaping the following character.
    ```py
    >>> r'wt\"f' == 'wt\\"f'
    True
    >>> print(repr(r'wt\"f')
    'wt\\"f'

    >>> print("\n")

    >>> print(r"\\n")
    '\\\\n'
    ```
- This means when a parser encounters a backslash in a raw string, it expects another character following it. And in our case (`print(r"\")`), the backslash escaped the trailing quote, leaving the parser without a terminating quote (hence the `SyntaxError`). That's why backslashes don't work at the end of a raw string.

---

### ▶ not knot!
<!-- Example ID: 7034deb1-7443-417d-94ee-29a800524de8 --->
```py
x = True
y = False
```

**Output:**
```py
>>> not x == y
True
>>> x == not y
  File "<input>", line 1
    x == not y
           ^
SyntaxError: invalid syntax
```

#### 💡 Explanation:

* Operator precedence affects how an expression is evaluated, and `==` operator has higher precedence than `not` operator in Python.
* So `not x == y` is equivalent to `not (x == y)` which is equivalent to `not (True == False)` finally evaluating to `True`.
* But `x == not y` raises a `SyntaxError` because it can be thought of being equivalent to `(x == not) y` and not `x == (not y)` which you might have expected at first sight.
* The parser expected the `not` token to be a part of the `not in` operator (because both `==` and `not in` operators have the same precedence), but after not being able to find an `in` token following the `not` token, it raises a `SyntaxError`.

---

### ▶ Half triple-quoted strings
<!-- Example ID: c55da3e2-1034-43b9-abeb-a7a970a2ad9e --->
**Output:**
```py
>>> print('wtfpython''')
wtfpython
>>> print("wtfpython""")
wtfpython
>>> # The following statements raise `SyntaxError`
>>> # print('''wtfpython')
>>> # print("""wtfpython")
  File "<input>", line 3
    print("""wtfpython")
                        ^
SyntaxError: EOF while scanning triple-quoted string literal
```

#### 💡 Explanation:
+ Python supports implicit [string literal concatenation](https://docs.python.org/2/reference/lexical_analysis.html#string-literal-concatenation), Example,
  ```
  >>> print("wtf" "python")
  wtfpython
  >>> print("wtf" "") # or "wtf"""
  wtf
  ```
+ `'''` and `"""` are also string delimiters in Python which causes a SyntaxError because the Python interpreter was expecting a terminating triple quote as delimiter while scanning the currently encountered triple quoted string literal.

---

### ▶ What's wrong with booleans?
<!-- Example ID: 0bba5fa7-9e6d-4cd2-8b94-952d061af5dd --->
1\.

```py
# A simple example to count the number of booleans and
# integers in an iterable of mixed data types.
mixed_list = [False, 1.0, "some_string", 3, True, [], False]
integers_found_so_far = 0
booleans_found_so_far = 0

for item in mixed_list:
    if isinstance(item, int):
        integers_found_so_far += 1
    elif isinstance(item, bool):
        booleans_found_so_far += 1
```

**Output:**
```py
>>> integers_found_so_far
4
>>> booleans_found_so_far
0
```


2\.
```py
>>> some_bool = True
>>> "wtf" * some_bool
'wtf'
>>> some_bool = False
>>> "wtf" * some_bool
''
```

3\.

```py
def tell_truth():
    True = False
    if True == False:
        print("I have lost faith in truth!")
```

**Output (< 3.x):**

```py
>>> tell_truth()
I have lost faith in truth!
```



#### 💡 Explanation:

* `bool` is a subclass of `int` in Python
    
    ```py
    >>> issubclass(bool, int)
    True
    >>> issubclass(int, bool)
    False
    ```
    
* And thus, `True` and `False` are instances of `int`
  ```py
  >>> isinstance(True, int)
  True
  >>> isinstance(False, int)
  True
  ```

* The integer value of `True` is `1` and that of `False` is `0`.
  ```py
  >>> int(True)
  1
  >>> int(False)
  0
  ```

* See this StackOverflow [answer](https://stackoverflow.com/a/8169049/4354153) for the rationale behind it.

* Initially, Python used to have no `bool` type (people used 0 for false and non-zero value like 1 for true).  `True`, `False`, and a `bool` type was added in 2.x versions, but, for backward compatibility, `True` and `False` couldn't be made constants. They just were built-in variables, and it was possible to reassign them

* Python 3 was backward-incompatible, the issue was finally fixed, and thus the last snippet won't work with Python 3.x!

---

### ▶ Class attributes and instance attributes
<!-- Example ID: 6f332208-33bd-482d-8106-42863b739ed9 --->
1\.
```py
class A:
    x = 1

class B(A):
    pass

class C(A):
    pass
```

**Output:**
```py
>>> A.x, B.x, C.x
(1, 1, 1)
>>> B.x = 2
>>> A.x, B.x, C.x
(1, 2, 1)
>>> A.x = 3
>>> A.x, B.x, C.x # C.x changed, but B.x didn't
(3, 2, 3)
>>> a = A()
>>> a.x, A.x
(3, 3)
>>> a.x += 1
>>> a.x, A.x
(4, 3)
```

2\.
```py
class SomeClass:
    some_var = 15
    some_list = [5]
    another_list = [5]
    def __init__(self, x):
        self.some_var = x + 1
        self.some_list = self.some_list + [x]
        self.another_list += [x]
```

**Output:**

```py
>>> some_obj = SomeClass(420)
>>> some_obj.some_list
[5, 420]
>>> some_obj.another_list
[5, 420]
>>> another_obj = SomeClass(111)
>>> another_obj.some_list
[5, 111]
>>> another_obj.another_list
[5, 420, 111]
>>> another_obj.another_list is SomeClass.another_list
True
>>> another_obj.another_list is some_obj.another_list
True
```

#### 💡 Explanation:

* Class variables and variables in class instances are internally handled as dictionaries of a class object. If a variable name is not found in the dictionary of the current class, the parent classes are searched for it.
* The `+=` operator modifies the mutable object in-place without creating a new object. So changing the attribute of one instance affects the other instances and the class attribute as well.

---

### ▶ Non-reflexive class method *

<!-- Example ID: 3649771a-f733-413c-8060-3f9f167b83fd -->

```py
class SomeClass:
        def instance_method(self):
                pass
        
        @classmethod
        def class_method(cls):
                pass
```

**Output:**

```py
>>> SomeClass.instance_method is SomeClass.instance_method
True
>>> SomeClass.class_method is SomeClass.class_method
False
>>> id(SomeClass.class_method) == id(SomeClass.class_method)
True
```

#### 💡 Explanation:

- The reason `SomeClass.class_method is SomeClass.class_method` is `False` is due to the `@classmethod` decorator. 

  ```py
  >>> SomeClass.instance_method
  <function __main__.SomeClass.instance_method(self)>
  >>> SomeClass.class_method
  <bound method SomeClass.class_method of <class '__main__.SomeClass'>
  ```

  A new bound method every time `SomeClass.class_method` is accessed.

-  `id(SomeClass.class_method) == id(SomeClass.class_method)` returned `True` because the second allocation of memory for `class_method` happened at the same location of first deallocation (See Deep Down, we're all the same example for more detailed explanation). 

---


### ▶ yielding None
<!-- Example ID: 5a40c241-2c30-40d0-8ba9-cf7e097b3b53 --->
```py
some_iterable = ('a', 'b')

def some_func(val):
    return "something"
```

**Output (<= 3.7.x):**

```py
>>> [x for x in some_iterable]
['a', 'b']
>>> [(yield x) for x in some_iterable]
<generator object <listcomp> at 0x7f70b0a4ad58>
>>> list([(yield x) for x in some_iterable])
['a', 'b']
>>> list((yield x) for x in some_iterable)
['a', None, 'b', None]
>>> list(some_func((yield x)) for x in some_iterable)
['a', 'something', 'b', 'something']
```

#### 💡 Explanation:
- This is a bug in CPython's handling of `yield` in generators and comprehensions.
- Source and explanation can be found here: https://stackoverflow.com/questions/32139885/yield-in-list-comprehensions-and-generator-expressions
- Related bug report: http://bugs.python.org/issue10544
- Python 3.8+ no longer allows `yield` inside list comprehension and will throw a `SyntaxError`.

---


### ▶ Yielding from... return! *
<!-- Example ID: 5626d8ef-8802-49c2-adbc-7cda5c550816 --->
1\.

```py
def some_func(x):
    if x == 3:
        return ["wtf"]
    else:
        yield from range(x)
```

**Output (> 3.3):**

```py
>>> list(some_func(3))
[]
```

Where did the `"wtf"` go? Is it due to some special effect of `yield from`? Let's validate that,

2\.

```py
def some_func(x):
    if x == 3:
        return ["wtf"]
    else:
        for i in range(x):
          yield i
```

**Output:**

```py
>>> list(some_func(3))
[]
```

The same result, this didn't work either.

#### 💡 Explanation:

+ From Python 3.3 onwards, it became possible to use `return` statement with values inside generators (See [PEP380](https://www.python.org/dev/peps/pep-0380/)). The [official docs](https://www.python.org/dev/peps/pep-0380/#enhancements-to-stopiteration) say that,

> "... `return expr` in a generator causes `StopIteration(expr)` to be raised upon exit from the generator."

+ In the case of `some_func(3)`, `StopIteration` is raised at the beginning because of `return` statement. The `StopIteration` exception is automatically caught inside the `list(...)` wrapper and the `for` loop. Therefore, the above two snippets result in an empty list.

+ To get `["wtf"]` from the generator `some_func` we need to catch the `StopIteration` exception,

  ```py
  try:
      next(some_func(3))
  except StopIteration as e:
      some_string = e.value
  ```

  ```py
  >>> some_string
  ["wtf"]
  ```

---

### ▶ Nan-reflexivity *

<!-- Example ID: 59bee91a-36e0-47a4-8c7d-aa89bf1d3976 --->

1\.

```py
a = float('inf')
b = float('nan')
c = float('-iNf')  # These strings are case-insensitive
d = float('nan')
```

**Output:**

```py
>>> a
inf
>>> b
nan
>>> c
-inf
>>> float('some_other_string')
ValueError: could not convert string to float: some_other_string
>>> a == -c # inf==inf
True
>>> None == None # None == None
True
>>> b == d # but nan!=nan
False
>>> 50 / a
0.0
>>> a / a
nan
>>> 23 + b
nan
```

2\.

```py
>>> x = float('nan')
>>> y = x / x
>>> y is y # identity holds
True
>>> y == y # equality fails of y
False
>>> [y] == [y] # but the equality succeeds for the list containing y
True
```



#### 💡 Explanation:

- `'inf'` and `'nan'` are special strings (case-insensitive), which, when explicitly typecast-ed to `float` type, are used to represent mathematical "infinity" and "not a number" respectively.

- Since according to IEEE standards ` NaN != NaN`, obeying this rule breaks the reflexivity assumption of a collection element in Python i.e. if `x` is a part of a collection like `list`, the implementations like comparison are based on the assumption that `x == x`.  Because of this assumption, the identity is compared first (since it's faster) while comparing two elements, and the values are compared only when the identities mismatch. The following snippet will make things clearer,

  ```py
  >>> x = float('nan')
  >>> x == x, [x] == [x]
  (False, True)
  >>> y = float('nan')
  >>> y == y, [y] == [y]
  (False, True)
  >>> x == y, [x] == [y]
  (False, False)
  ```

  Since the identities of `x` and `y` are different, the values are considered, which are also different; hence the comparison returns `False` this time.

- Interesting read: [Reflexivity, and other pillars of civilization](https://bertrandmeyer.com/2010/02/06/reflexivity-and-other-pillars-of-civilization/)

---

### ▶ Mutating the immutable!

<!-- Example ID: 15a9e782-1695-43ea-817a-a9208f6bb33d --->

This might seem trivial if you know how references work in Python.

```py
some_tuple = ("A", "tuple", "with", "values")
another_tuple = ([1, 2], [3, 4], [5, 6])
```

**Output:**
```py
>>> some_tuple[2] = "change this"
TypeError: 'tuple' object does not support item assignment
>>> another_tuple[2].append(1000) #This throws no error
>>> another_tuple
([1, 2], [3, 4], [5, 6, 1000])
>>> another_tuple[2] += [99, 999]
TypeError: 'tuple' object does not support item assignment
>>> another_tuple
([1, 2], [3, 4], [5, 6, 1000, 99, 999])
```

But I thought tuples were immutable...

#### 💡 Explanation:

* Quoting from https://docs.python.org/2/reference/datamodel.html

    > Immutable sequences
        An object of an immutable sequence type cannot change once it is created. (If the object contains references to other objects, these other objects may be mutable and may be modified; however, the collection of objects directly referenced by an immutable object cannot change.)

* `+=` operator changes the list in-place. The item assignment doesn't work, but when the exception occurs, the item has already been changed in place.

---

### ▶ The disappearing variable from outer scope
<!-- Example ID: 7f1e71b6-cb3e-44fb-aa47-87ef1b7decc8 --->

```py
e = 7
try:
    raise Exception()
except Exception as e:
    pass
```

**Output (Python 2.x):**
```py
>>> print(e)
# prints nothing
```

**Output (Python 3.x):**
```py
>>> print(e)
NameError: name 'e' is not defined
```

#### 💡 Explanation:

* Source: https://docs.python.org/3/reference/compound_stmts.html#except

  When an exception has been assigned using `as` target, it is cleared at the end of the `except` clause. This is as if

  ```py
  except E as N:
      foo
  ```

  was translated into

  ```py
  except E as N:
      try:
          foo
      finally:
          del N
  ```

  This means the exception must be assigned to a different name to be able to refer to it after the except clause. Exceptions are cleared because, with the traceback attached to them, they form a reference cycle with the stack frame, keeping all locals in that frame alive until the next garbage collection occurs.

* The clauses are not scoped in Python. Everything in the example is present in the same scope, and the variable `e` got removed due to the execution of the `except` clause. The same is not the case with functions that have their separate inner-scopes. The example below illustrates this:

     ```py
     def f(x):
         del(x)
         print(x)

     x = 5
     y = [5, 4, 3]
     ```

     **Output:**
     ```py
     >>>f(x)
     UnboundLocalError: local variable 'x' referenced before assignment
     >>>f(y)
     UnboundLocalError: local variable 'x' referenced before assignment
     >>> x
     5
     >>> y
     [5, 4, 3]
     ```

* In Python 2.x, the variable name `e` gets assigned to `Exception()` instance, so when you try to print, it prints nothing.

    **Output (Python 2.x):**
    ```py
    >>> e
    Exception()
    >>> print e
    # Nothing is printed!
    ```

---


### ▶ The mysterious key type conversion
<!-- Example ID: 00f42dd0-b9ef-408d-9e39-1bc209ce3f36 --->
```py
class SomeClass(str):
    pass

some_dict = {'s': 42}
```

**Output:**
```py
>>> type(list(some_dict.keys())[0])
str
>>> s = SomeClass('s')
>>> some_dict[s] = 40
>>> some_dict # expected: Two different keys-value pairs
{'s': 40}
>>> type(list(some_dict.keys())[0])
str
```

#### 💡 Explanation:

* Both the object `s` and the string `"s"` hash to the same value because `SomeClass` inherits the `__hash__` method of `str` class.
* `SomeClass("s") == "s"` evaluates to `True` because `SomeClass` also inherits `__eq__` method from `str` class.
* Since both the objects hash to the same value and are equal, they are represented by the same key in the dictionary.
* For the desired behavior, we can redefine the `__eq__` method in `SomeClass`
  ```py
  class SomeClass(str):
    def __eq__(self, other):
        return (
            type(self) is SomeClass
            and type(other) is SomeClass
            and super().__eq__(other)
        )

    # When we define a custom __eq__, Python stops automatically inheriting the
    # __hash__ method, so we need to define it as well
    __hash__ = str.__hash__

  some_dict = {'s':42}
  ```

  **Output:**
  ```py
  >>> s = SomeClass('s')
  >>> some_dict[s] = 40
  >>> some_dict
  {'s': 40, 's': 42}
  >>> keys = list(some_dict.keys())
  >>> type(keys[0]), type(keys[1])
  (__main__.SomeClass, str)
  ```

---

### ▶ Let's see if you can guess this?
<!-- Example ID: 81aa9fbe-bd63-4283-b56d-6fdd14c9105e --->
```py
a, b = a[b] = {}, 5
```

**Output:**
```py
>>> a
{5: ({...}, 5)}
```

#### 💡 Explanation:

* According to [Python language reference](https://docs.python.org/2/reference/simple_stmts.html#assignment-statements), assignment statements have the form
  ```
  (target_list "=")+ (expression_list | yield_expression)
  ```
  and
  
> An assignment statement evaluates the expression list (remember that this can be a single expression or a comma-separated list, the latter yielding a tuple) and assigns the single resulting object to each of the target lists, from left to right.

* The `+` in `(target_list "=")+` means there can be **one or more** target lists. In this case, target lists are `a, b` and `a[b]` (note the expression list is exactly one, which in our case is `{}, 5`).

* After the expression list is evaluated, its value is unpacked to the target lists from **left to right**. So, in our case, first the `{}, 5` tuple is unpacked to `a, b` and we now have `a = {}` and `b = 5`.

* `a` is now assigned to `{}`, which is a mutable object.

* The second target list is `a[b]` (you may expect this to throw an error because both `a` and `b` have not been defined in the statements before. But remember, we just assigned `a` to `{}` and `b` to `5`).

* Now, we are setting the key `5` in the dictionary to the tuple `({}, 5)` creating a circular reference (the `{...}` in the output refers to the same object that `a` is already referencing). Another simpler example of circular reference could be
  ```py
  >>> some_list = some_list[0] = [0]
  >>> some_list
  [[...]]
  >>> some_list[0]
  [[...]]
  >>> some_list is some_list[0]
  True
  >>> some_list[0][0][0][0][0][0] == some_list
  True
  ```
  Similar is the case in our example (`a[b][0]` is the same object as `a`)

* So to sum it up, you can break the example down to
  ```py
  a, b = {}, 5
  a[b] = a, b
  ```
  And the circular reference can be justified by the fact that `a[b][0]` is the same object as `a`
  ```py
  >>> a[b][0] is a
  True
  ```

---
---

## Section: Slippery Slopes

### ▶ Modifying a dictionary while iterating over it
<!-- Example ID: b4e5cdfb-c3a8-4112-bd38-e2356d801c41 --->
```py
x = {0: None}

for i in x:
    del x[i]
    x[i+1] = None
    print(i)
```

**Output (Python 2.7- Python 3.5):**

```
0
1
2
3
4
5
6
7
```

Yes, it runs for exactly **eight** times and stops.

#### 💡 Explanation:

* Iteration over a dictionary that you edit at the same time is not supported.
* It runs eight times because that's the point at which the dictionary resizes to hold more keys (we have eight deletion entries, so a resize is needed). This is actually an implementation detail.
* How deleted keys are handled and when the resize occurs might be different for different Python implementations.
* So for Python versions other than Python 2.7 - Python 3.5, the count might be different from 8 (but whatever the count is, it's going to be the same every time you run it). You can find some discussion around this [here](https://github.com/satwikkansal/wtfpython/issues/53) or in [this](https://stackoverflow.com/questions/44763802/bug-in-python-dict) StackOverflow thread.
* Python 3.8 onwards, you'll see `RuntimeError: dictionary keys changed during iteration` exception if you try to do this.

---

### ▶ Stubborn `del` operation
<!-- Example ID: 777ed4fd-3a2d-466f-95e7-c4058e61d78e --->
<!-- read-only -->

```py
class SomeClass:
    def __del__(self):
        print("Deleted!")
```

**Output:**
1\.
```py
>>> x = SomeClass()
>>> y = x
>>> del x # this should print "Deleted!"
>>> del y
Deleted!
```

Phew, deleted at last. You might have guessed what saved from `__del__` being called in our first attempt to delete `x`. Let's add more twists to the example.

2\.
```py
>>> x = SomeClass()
>>> y = x
>>> del x
>>> y # check if y exists
<__main__.SomeClass instance at 0x7f98a1a67fc8>
>>> del y # Like previously, this should print "Deleted!"
>>> globals() # oh, it didn't. Let's check all our global variables and confirm
Deleted!
{'__builtins__': <module '__builtin__' (built-in)>, 'SomeClass': <class __main__.SomeClass at 0x7f98a1a5f668>, '__package__': None, '__name__': '__main__', '__doc__': None}
```

Okay, now it's deleted :confused:

#### 💡 Explanation:
+ `del x` doesn’t directly call `x.__del__()`.
+ Whenever `del x` is encountered, Python decrements the reference count for `x` by one, and `x.__del__()` when x’s reference count reaches zero.
+ In the second output snippet, `y.__del__()` was not called because the previous statement (`>>> y`) in the interactive interpreter created another reference to the same object, thus preventing the reference count from reaching zero when `del y` was encountered.
+ Calling `globals` caused the existing reference to be destroyed, and hence we can see "Deleted!" being printed (finally!).

---

### ▶ The out of scope variable
<!-- Example ID: 75c03015-7be9-4289-9e22-4f5fdda056f7 --->
```py
a = 1
def some_func():
    return a

def another_func():
    a += 1
    return a
```

**Output:**
```py
>>> some_func()
1
>>> another_func()
UnboundLocalError: local variable 'a' referenced before assignment
```

#### 💡 Explanation:
* When you make an assignment to a variable in scope, it becomes local to that scope. So `a` becomes local to the scope of `another_func`,  but it has not been initialized previously in the same scope, which throws an error.
* Read [this](http://sebastianraschka.com/Articles/2014_python_scope_and_namespaces.html) short but an awesome guide to learn more about how namespaces and scope resolution works in Python.
* To modify the outer scope variable `a` in `another_func`, use `global` keyword.
  ```py
  def another_func()
      global a
      a += 1
      return a
  ```

  **Output:**
  ```py
  >>> another_func()
  2
  ```

---

### ▶ Deleting a list item while iterating
<!-- Example ID: 4cc52d4e-d42b-4e09-b25f-fbf5699b7d4e --->
```py
list_1 = [1, 2, 3, 4]
list_2 = [1, 2, 3, 4]
list_3 = [1, 2, 3, 4]
list_4 = [1, 2, 3, 4]

for idx, item in enumerate(list_1):
    del item

for idx, item in enumerate(list_2):
    list_2.remove(item)

for idx, item in enumerate(list_3[:]):
    list_3.remove(item)

for idx, item in enumerate(list_4):
    list_4.pop(idx)
```

**Output:**
```py
>>> list_1
[1, 2, 3, 4]
>>> list_2
[2, 4]
>>> list_3
[]
>>> list_4
[2, 4]
```

Can you guess why the output is `[2, 4]`?

#### 💡 Explanation:

* It's never a good idea to change the object you're iterating over. The correct way to do so is to iterate over a copy of the object instead, and `list_3[:]` does just that.

     ```py
     >>> some_list = [1, 2, 3, 4]
     >>> id(some_list)
     139798789457608
     >>> id(some_list[:]) # Notice that python creates new object for sliced list.
     139798779601192
     ```

**Difference between `del`, `remove`, and `pop`:**
* `del var_name` just removes the binding of the `var_name` from the local or global namespace (That's why the `list_1` is unaffected).
* `remove` removes the first matching value, not a specific index, raises `ValueError` if the value is not found.
* `pop` removes the element at a specific index and returns it, raises `IndexError` if an invalid index is specified.

**Why the output is `[2, 4]`?**
- The list iteration is done index by index, and when we remove `1` from `list_2` or `list_4`, the contents of the lists are now `[2, 3, 4]`. The remaining elements are shifted down, i.e., `2` is at index 0, and `3` is at index 1. Since the next iteration is going to look at index 1 (which is the `3`), the `2` gets skipped entirely. A similar thing will happen with every alternate element in the list sequence.

* Refer to this StackOverflow [thread](https://stackoverflow.com/questions/45946228/what-happens-when-you-try-to-delete-a-list-element-while-iterating-over-it) explaining the example
* See also this nice StackOverflow [thread](https://stackoverflow.com/questions/45877614/how-to-change-all-the-dictionary-keys-in-a-for-loop-with-d-items) for a similar example related to dictionaries in Python.

---


### ▶ Lossy zip of iterators *
<!-- Example ID: c28ed154-e59f-4070-8eb6-8967a4acac6d --->

```py
>>> numbers = list(range(7))
>>> numbers
[0, 1, 2, 3, 4, 5, 6]
>>> first_three, remaining = numbers[:3], numbers[3:]
>>> first_three, remaining
([0, 1, 2], [3, 4, 5, 6])
>>> numbers_iter = iter(numbers)
>>> list(zip(numbers_iter, first_three)) 
[(0, 0), (1, 1), (2, 2)]
# so far so good, let's zip the remaining
>>> list(zip(numbers_iter, remaining))
[(4, 3), (5, 4), (6, 5)]
```
Where did element `3` go from the `numbers` list?

#### 💡 Explanation:

- From Python [docs](https://docs.python.org/3.3/library/functions.html#zip), here's an approximate implementation of zip function,
    ```py
    def zip(*iterables):
        sentinel = object()
        iterators = [iter(it) for it in iterables]
        while iterators:
            result = []
            for it in iterators:
                elem = next(it, sentinel)
                if elem is sentinel: return
                result.append(elem)
            yield tuple(result)
    ```
- So the function takes in arbitrary number of itreable objects, adds each of their items to the `result` list by calling the `next` function on them, and stops whenever any of the iterable is exhausted. 
- The caveat here is when any iterable is exhausted, the existing elements in the `result` list are discarded. That's what happened with `3` in the `numbers_iter`.
- The correct way to do the above using `zip` would be,
    ```py
    >>> numbers = list(range(7))
    >>> numbers_iter = iter(numbers)
    >>> list(zip(first_three, numbers_iter))
    [(0, 0), (1, 1), (2, 2)]
    >>> list(zip(remaining, numbers_iter))
    [(3, 3), (4, 4), (5, 5), (6, 6)]
    ```
    The first argument of zip should be the one with fewest elements.

---

### ▶ Loop variables leaking out!
<!-- Example ID: ccec7bf6-7679-4963-907a-1cd8587be9ea --->
1\.
```py
for x in range(7):
    if x == 6:
        print(x, ': for x inside loop')
print(x, ': x in global')
```

**Output:**
```py
6 : for x inside loop
6 : x in global
```

But `x` was never defined outside the scope of for loop...

2\.
```py
# This time let's initialize x first
x = -1
for x in range(7):
    if x == 6:
        print(x, ': for x inside loop')
print(x, ': x in global')
```

**Output:**
```py
6 : for x inside loop
6 : x in global
```

3\.

**Output (Python 2.x):**
```py
>>> x = 1
>>> print([x for x in range(5)])
[0, 1, 2, 3, 4]
>>> print(x)
4
```

**Output (Python 3.x):**
```py
>>> x = 1
>>> print([x for x in range(5)])
[0, 1, 2, 3, 4]
>>> print(x)
1
```

#### 💡 Explanation:

- In Python, for-loops use the scope they exist in and leave their defined loop-variable behind. This also applies if we explicitly defined the for-loop variable in the global namespace before. In this case, it will rebind the existing variable.

- The differences in the output of Python 2.x and Python 3.x interpreters for list comprehension example can be explained by following change documented in [What’s New In Python 3.0](https://docs.python.org/3/whatsnew/3.0.html) changelog:

    > "List comprehensions no longer support the syntactic form `[... for var in item1, item2, ...]`. Use `[... for var in (item1, item2, ...)]` instead. Also, note that list comprehensions have different semantics: they are closer to syntactic sugar for a generator expression inside a `list()` constructor, and in particular, the loop control variables are no longer leaked into the surrounding scope."

---

### ▶ Beware of default mutable arguments!
<!-- Example ID: 7d42dade-e20d-4a7b-9ed7-16fb58505fe9 --->

```py
def some_func(default_arg=[]):
    default_arg.append("some_string")
    return default_arg
```

**Output:**
```py
>>> some_func()
['some_string']
>>> some_func()
['some_string', 'some_string']
>>> some_func([])
['some_string']
>>> some_func()
['some_string', 'some_string', 'some_string']
```

#### 💡 Explanation:

- The default mutable arguments of functions in Python aren't really initialized every time you call the function. Instead, the recently assigned value to them is used as the default value. When we explicitly passed `[]` to `some_func` as the argument, the default value of the `default_arg` variable was not used, so the function returned as expected.

    ```py
    def some_func(default_arg=[]):
        default_arg.append("some_string")
        return default_arg
    ```

    **Output:**
    ```py
    >>> some_func.__defaults__ #This will show the default argument values for the function
    ([],)
    >>> some_func()
    >>> some_func.__defaults__
    (['some_string'],)
    >>> some_func()
    >>> some_func.__defaults__
    (['some_string', 'some_string'],)
    >>> some_func([])
    >>> some_func.__defaults__
    (['some_string', 'some_string'],)
    ```

- A common practice to avoid bugs due to mutable arguments is to assign `None` as the default value and later check if any value is passed to the function corresponding to that argument. Example:

    ```py
    def some_func(default_arg=None):
        if not default_arg:
            default_arg = []
        default_arg.append("some_string")
        return default_arg
    ```

---

### ▶ Catching the Exceptions
<!-- Example ID: b5ca5e6a-47b9-4f69-9375-cda0f8c6755d --->
```py
some_list = [1, 2, 3]
try:
    # This should raise an ``IndexError``
    print(some_list[4])
except IndexError, ValueError:
    print("Caught!")

try:
    # This should raise a ``ValueError``
    some_list.remove(4)
except IndexError, ValueError:
    print("Caught again!")
```

**Output (Python 2.x):**
```py
Caught!

ValueError: list.remove(x): x not in list
```

**Output (Python 3.x):**
```py
  File "<input>", line 3
    except IndexError, ValueError:
                     ^
SyntaxError: invalid syntax
```

#### 💡 Explanation

* To add multiple Exceptions to the except clause, you need to pass them as parenthesized tuple as the first argument. The second argument is an optional name, which when supplied will bind the Exception instance that has been raised. Example,
  ```py
  some_list = [1, 2, 3]
  try:
     # This should raise a ``ValueError``
     some_list.remove(4)
  except (IndexError, ValueError), e:
     print("Caught again!")
     print(e)
  ```
  **Output (Python 2.x):**
  ```
  Caught again!
  list.remove(x): x not in list
  ```
  **Output (Python 3.x):**
  ```py
    File "<input>", line 4
      except (IndexError, ValueError), e:
                                       ^
  IndentationError: unindent does not match any outer indentation level
  ```

* Separating the exception from the variable with a comma is deprecated and does not work in Python 3; the correct way is to use `as`. Example,
  ```py
  some_list = [1, 2, 3]
  try:
      some_list.remove(4)

  except (IndexError, ValueError) as e:
      print("Caught again!")
      print(e)
  ```
  **Output:**
  ```
  Caught again!
  list.remove(x): x not in list
  ```

---

### ▶ Same operands, different story!
<!-- Example ID: ca052cdf-dd2d-4105-b936-65c28adc18a0 --->
1\.
```py
a = [1, 2, 3, 4]
b = a
a = a + [5, 6, 7, 8]
```

**Output:**
```py
>>> a
[1, 2, 3, 4, 5, 6, 7, 8]
>>> b
[1, 2, 3, 4]
```

2\.
```py
a = [1, 2, 3, 4]
b = a
a += [5, 6, 7, 8]
```

**Output:**
```py
>>> a
[1, 2, 3, 4, 5, 6, 7, 8]
>>> b
[1, 2, 3, 4, 5, 6, 7, 8]
```

#### 💡 Explanation:

*  `a += b` doesn't always behave the same way as `a = a + b`.  Classes *may* implement the *`op=`* operators differently, and lists do this.

* The expression `a = a + [5,6,7,8]` generates a new list and sets `a`'s reference to that new list, leaving `b` unchanged.

* The expression `a += [5,6,7,8]` is actually mapped to an "extend" function that operates on the list such that `a` and `b` still point to the same list that has been modified in-place.

---


### ▶ Be careful with chained operations
<!-- Example ID: 07974979-9c86-4720-80bd-467aa19470d9 --->
```py
>>> (False == False) in [False] # makes sense
False
>>> False == (False in [False]) # makes sense
False
>>> False == False in [False] # now what?
True

>>> True is False == False
False
>>> False is False is False
True

>>> 1 > 0 < 1
True
>>> (1 > 0) < 1
False
>>> 1 > (0 < 1)
False
```

#### 💡 Explanation:

As per https://docs.python.org/2/reference/expressions.html#not-in

> Formally, if a, b, c, ..., y, z are expressions and op1, op2, ..., opN are comparison operators, then a op1 b op2 c ... y opN z is equivalent to a op1 b and b op2 c and ... y opN z, except that each expression is evaluated at most once.

While such behavior might seem silly to you in the above examples, it's fantastic with stuff like `a == b == c` and `0 <= x <= 100`.

* `False is False is False` is equivalent to `(False is False) and (False is False)`
* `True is False == False` is equivalent to `True is False and False == False` and since the first part of the statement (`True is False`) evaluates to `False`, the overall expression evaluates to `False`.
* `1 > 0 < 1` is equivalent to `1 > 0 and 0 < 1` which evaluates to `True`.
* The expression `(1 > 0) < 1` is equivalent to `True < 1` and
  ```py
  >>> int(True)
  1
  >>> True + 1 #not relevant for this example, but just for fun
  2
  ```
  So, `1 < 1` evaluates to `False`

---

### ▶ Name resolution ignoring class scope
<!-- Example ID: 03f73d96-151c-4929-b0a8-f74430788324 --->
1\.
```py
x = 5
class SomeClass:
    x = 17
    y = (x for i in range(10))
```

**Output:**
```py
>>> list(SomeClass.y)[0]
5
```

2\.
```py
x = 5
class SomeClass:
    x = 17
    y = [x for i in range(10)]
```

**Output (Python 2.x):**
```py
>>> SomeClass.y[0]
17
```

**Output (Python 3.x):**
```py
>>> SomeClass.y[0]
5
```

#### 💡 Explanation
- Scopes nested inside class definition ignore names bound at the class level.
- A generator expression has its own scope.
- Starting from Python 3.X, list comprehensions also have their own scope.

---

### ▶ Needles in a Haystack *

<!-- Example ID: 52a199b1-989a-4b28-8910-dff562cebba9 --->

I haven't met even a single experience Pythonist till date who has not come across one or more of the following scenarios,

1\.

```py
x, y = (0, 1) if True else None, None
```

**Output:**

```py
>>> x, y  # expected (0, 1)
((0, 1), None)
```

2\.

```py
t = ('one', 'two')
for i in t:
    print(i)

t = ('one')
for i in t:
    print(i)

t = ()
print(t)
```

**Output:**

```py
one
two
o
n
e
tuple()
```

3\.

```
ten_words_list = [
    "some",
    "very",
    "big",
    "list",
    "that"
    "consists",
    "of",
    "exactly",
    "ten",
    "words"
]
```

**Output**

```py
>>> len(ten_words_list)
9
```

4\. Not asserting strongly enough

```py
a = "python"
b = "javascript"
```

**Output:**

```py
# An assert statement with an assertion failure message.
>>> assert(a == b, "Both languages are different")
# No AssertionError is raised
```

5\.

```py
some_list = [1, 2, 3]
some_dict = {
  "key_1": 1,
  "key_2": 2,
  "key_3": 3
}

some_list = some_list.append(4) 
some_dict = some_dict.update({"key_4": 4})
```

**Output:**

```py
>>> print(some_list)
None
>>> print(some_dict)
None
```

6\.

```py
def some_recursive_func(a):
    if a[0] == 0:
        return 
    a[0] -= 1
    some_recursive_func(a)
    return a

def similar_recursive_func(a):
        if a == 0:
                return a
        a -= 1
        similar_recursive_func(a)
        return a
```

**Output:**

```py
>>> some_recursive_func([5, 0])
[0, 0]
>>> similar_recursive_func(5)
4
```

#### 💡 Explanation:

* For 1, the correct statement for expected behavior is `x, y = (0, 1) if True else (None, None)`.

* For 2, the correct statement for expected behavior is `t = ('one',)` or `t = 'one',` (missing comma) otherwise the interpreter considers `t` to be a `str` and iterates over it character by character.

* `()` is a special token and denotes empty `tuple`.

* In 3, as you might have already figured out, there's a missing comma after 5th element (`"that"`) in the list. So by implicit string literal concatenation,

  ```py
  >>> ten_words_list
  ['some', 'very', 'big', 'list', 'thatconsists', 'of', 'exactly', 'ten', 'words']
  ```

* No `AssertionError` was raised in 4th snippet because instead of asserting the individual expression `a == b`, we're asserting entire tuple. The following snippet will clear things up,

  ```py
  >>> a = "python"
  >>> b = "javascript"
  >>> assert a == b
  Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
  AssertionError
  
  >>> assert (a == b, "Values are not equal")
  <stdin>:1: SyntaxWarning: assertion is always true, perhaps remove parentheses?
  
  >>> assert a == b, "Values are not equal"
  Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
  AssertionError: Values aren not equal
  ```

* As for the fifth snippet, most methods that modify the items of sequence/mapping objects like `list.append`, `dict.update`, `list.sort`, etc. modify the objects in-place and return `None`. The rationale behind this is to improve performance by avoiding making a copy of the object if the operation can be done in-place (Referred from [here](http://docs.python.org/2/faq/design.html#why-doesn-t-list-sort-return-the-sorted-list)).

* Last one should be fairly obvious, passing mutable object (like  `list` ) results in a call by reference, whereas an immutable object (like `int`)  results in a call by value.

* Being aware of these nitpicks can save you hours of debugging effort in the long run. 

---


### ▶ Splitsies *
<!-- Example ID: ec3168ba-a81a-4482-afb0-691f1cc8d65a --->
```py
>>> 'a'.split()
['a']

# is same as
>>> 'a'.split(' ')
['a']

# but
>>> len(''.split())
0

# isn't the same as
>>> len(''.split(' '))
1
```

#### 💡 Explanation:

- It might appear at first that the default separator for split is a single space `' '`, but as per the [docs](https://docs.python.org/2.7/library/stdtypes.html#str.split)
    >  If sep is not specified or is `None`, a different splitting algorithm is applied: runs of consecutive whitespace are regarded as a single separator, and the result will contain no empty strings at the start or end if the string has leading or trailing whitespace. Consequently, splitting an empty string or a string consisting of just whitespace with a None separator returns `[]`.
    > If sep is given, consecutive delimiters are not grouped together and are deemed to delimit empty strings (for example, `'1,,2'.split(',')` returns `['1', '', '2']`). Splitting an empty string with a specified separator returns `['']`.
- Noticing how the leading and trailing whitespaces are handled in the following snippet will make things clear,
    ```py
    >>> ' a '.split(' ')
    ['', 'a', '']
    >>> ' a '.split()
    ['a']
    >>> ''.split(' ')
    ['']
    ```

---

### ▶ Wild imports *
<!-- Example ID: 83deb561-bd55-4461-bb5e-77dd7f411e1c --->
<!-- read-only -->

```py
# File: module.py

def some_weird_name_func_():
    print("works!")

def _another_weird_name_func():
    print("works!")

```

**Output**

```py
>>> from module import *
>>> some_weird_name_func_()
"works!"
>>> _another_weird_name_func()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name '_another_weird_name_func' is not defined
```

#### 💡 Explanation:

- It is often advisable to not use wildcard imports. The first obvious reason for this is, in wildcard imports, the names with a leading underscore get imported. This may lead to errors during runtime.
- Had we used `from ... import a, b, c` syntax, the above `NameError` wouldn't have occurred.
    ```py
    >>> from module import some_weird_name_func_, _another_weird_name_func
    >>> _another_weird_name_func()
    works!
    ```
- If you really want to use wildcard imports, then you'd have to define the list `__all__` in your module that will contain a list of public objects that'll be available when we do wildcard imports.
    ```py
    __all__ = ['_another_weird_name_func']

    def some_weird_name_func_():
        print("works!")

    def _another_weird_name_func():
        print("works!")
    ```
    **Output**

    ```py
    >>> _another_weird_name_func()
    "works!"
    >>> some_weird_name_func_()
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'some_weird_name_func_' is not defined
    ```

---

### ▶ All sorted? *

<!-- Example ID: e5ff1eaf-8823-4738-b4ce-b73f7c9d5511 -->

```py
>>> x = 7, 8, 9
>>> sorted(x) == x
False
>>> sorted(x) == sorted(x)
True

>>> y = reversed(x)
>>> sorted(y) == sorted(y)
False
```

#### 💡 Explanation:

- The `sorted` method always returns a list, and comparing lists and tuples always returns `False` in Python. 

- ```py
  >>> [] == tuple()
  False
  >>> x = 7, 8, 9
  >>> type(x), type(sorted(x))
  (tuple, list)
  ```

- Unlike `sorted`, the `reversed` method returns an iterator. Why? Because sorting requires the iterator to be either modified in-place or use an extra container (a list), whereas reversing can simply work by iterating from the last index to the first.

- So during comparison `sorted(y) == sorted(y)`, the first call to `sorted()` will consume the iterator `y`, and the next call will just return an empty list.

  ```py
  >>> x = 7, 8, 9
  >>> y = reversed(x)
  >>> sorted(y), sorted(y)
  ([7, 8, 9], [])
  ```

---

### ▶ Midnight time doesn't exist?
<!-- Example ID: 1bce8294-5619-4d70-8ce3-fe0bade690d1 --->
```py
from datetime import datetime

midnight = datetime(2018, 1, 1, 0, 0)
midnight_time = midnight.time()

noon = datetime(2018, 1, 1, 12, 0)
noon_time = noon.time()

if midnight_time:
    print("Time at midnight is", midnight_time)

if noon_time:
    print("Time at noon is", noon_time)
```

**Output (< 3.5):**

```py
('Time at noon is', datetime.time(12, 0))
```
The midnight time is not printed.

#### 💡 Explanation:

Before Python 3.5, the boolean value for `datetime.time` object was considered to be `False` if it represented midnight in UTC. It is error-prone when using the `if obj:` syntax to check if the `obj` is null or some equivalent of "empty."

---
---



## Section: The Hidden treasures!

This section contains a few lesser-known and interesting things about Python that most beginners like me are unaware of (well, not anymore).

### ▶ Okay Python, Can you make me fly?
<!-- Example ID: a92f3645-1899-4d50-9721-0031be4aec3f --->
Well, here you go

```py
import antigravity
```

**Output:**
Sshh... It's a super-secret.

#### 💡 Explanation:
+ `antigravity` module is one of the few easter eggs released by Python developers.
+ `import antigravity` opens up a web browser pointing to the [classic XKCD comic](http://xkcd.com/353/) about Python.
+ Well, there's more to it. There's **another easter egg inside the easter egg**. If you look at the [code](https://github.com/python/cpython/blob/master/Lib/antigravity.py#L7-L17), there's a function defined that purports to implement the [XKCD's geohashing algorithm](https://xkcd.com/426/).

---

### ▶ `goto`, but why?
<!-- Example ID: 2aff961e-7fa5-4986-a18a-9e5894bd89fe --->

```py
from goto import goto, label
for i in range(9):
    for j in range(9):
        for k in range(9):
            print("I am trapped, please rescue!")
            if k == 2:
                goto .breakout # breaking out from a deeply nested loop
label .breakout
print("Freedom!")
```

**Output (Python 2.3):**
```py
I am trapped, please rescue!
I am trapped, please rescue!
Freedom!
```

#### 💡 Explanation:
- A working version of `goto` in Python was [announced](https://mail.python.org/pipermail/python-announce-list/2004-April/002982.html) as an April Fool's joke on 1st April 2004.
- Current versions of Python do not have this module.
- Although it works, but please don't use it. Here's the [reason](https://docs.python.org/3/faq/design.html#why-is-there-no-goto) to why `goto` is not present in Python.

---

### ▶ Brace yourself!
<!-- Example ID: 5c0c75f2-ddd9-4da3-ba49-c4be7ec39acf --->
If you are one of the people who doesn't like using whitespace in Python to denote scopes, you can use the C-style {} by importing,

```py
from __future__ import braces
```

**Output:**
```py
  File "some_file.py", line 1
    from __future__ import braces
SyntaxError: not a chance
```

Braces? No way! If you think that's disappointing, use Java. Okay, another surprising thing, can you find where's the `SyntaxError` raised in `__future__` module [code](https://github.com/python/cpython/blob/master/Lib/__future__.py)?

#### 💡 Explanation:
+ The `__future__` module is normally used to provide features from future versions of Python. The "future" in this specific context is however, ironic.
+ This is an easter egg concerned with the community's feelings on this issue.
+ The code is actually present [here](https://github.com/python/cpython/blob/025eb98dc0c1dc27404df6c544fc2944e0fa9f3a/Python/future.c#L49) in `future.c` file.
+ When the CPython compiler encounters a [future statement](https://docs.python.org/3.3/reference/simple_stmts.html#future-statements), it first runs the appropriate code in `future.c` before treating it as a normal import statement.

---

### ▶ Let's meet Friendly Language Uncle For Life
<!-- Example ID: 6427fae6-e959-462d-85da-ce4c94ce41be --->
**Output (Python 3.x)**
```py
>>> from __future__ import barry_as_FLUFL
>>> "Ruby" != "Python" # there's no doubt about it
  File "some_file.py", line 1
    "Ruby" != "Python"
              ^
SyntaxError: invalid syntax

>>> "Ruby" <> "Python"
True
```

There we go.

#### 💡 Explanation:
- This is relevant to [PEP-401](https://www.python.org/dev/peps/pep-0401/) released on April 1, 2009 (now you know, what it means).
- Quoting from the PEP-401
  
  > Recognized that the != inequality operator in Python 3.0 was a horrible, finger-pain inducing mistake, the FLUFL reinstates the <> diamond operator as the sole spelling.
- There were more things that Uncle Barry had to share in the PEP; you can read them [here](https://www.python.org/dev/peps/pep-0401/).
- It works well in an interactive environment, but it will raise a `SyntaxError` when you run via python file (see this [issue](https://github.com/satwikkansal/wtfpython/issues/94)). However, you can wrap the statement inside an `eval` or `compile` to get it working,
    ```py
    from __future__ import barry_as_FLUFL
    print(eval('"Ruby" <> "Python"'))
    ```

---

### ▶ Even Python understands that love is complicated
<!-- Example ID: b93cad9e-d341-45d1-999c-fcdce65bed25 --->
```py
import this
```

Wait, what's **this**? `this` is love :heart:

**Output:**
```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

It's the Zen of Python!

```py
>>> love = this
>>> this is love
True
>>> love is True
False
>>> love is False
False
>>> love is not True or False
True
>>> love is not True or False; love is love  # Love is complicated
True
```

#### 💡 Explanation:

* `this` module in Python is an easter egg for The Zen Of Python ([PEP 20](https://www.python.org/dev/peps/pep-0020)).
* And if you think that's already interesting enough, check out the implementation of [this.py](https://hg.python.org/cpython/file/c3896275c0f6/Lib/this.py). Interestingly, **the code for the Zen violates itself** (and that's probably the only place where this happens).
* Regarding the statement `love is not True or False; love is love`, ironic but it's self-explanatory (if not, please see the examples related to `is` and `is not` operators).

---

### ▶ Yes, it exists!
<!-- Example ID: 4286db3d-1ea7-47c9-8fb6-a9a04cac6e49 --->
**The `else` clause for loops.** One typical example might be:

```py
  def does_exists_num(l, to_find):
      for num in l:
          if num == to_find:
              print("Exists!")
              break
      else:
          print("Does not exist")
```

**Output:**
```py
>>> some_list = [1, 2, 3, 4, 5]
>>> does_exists_num(some_list, 4)
Exists!
>>> does_exists_num(some_list, -1)
Does not exist
```

**The `else` clause in exception handling.** An example,

```py
try:
    pass
except:
    print("Exception occurred!!!")
else:
    print("Try block executed successfully...")
```

**Output:**
```py
Try block executed successfully...
```

#### 💡 Explanation:
- The `else` clause after a loop is executed only when there's no explicit `break` after all the iterations. You can think of it as a "nobreak" clause.
- `else` clause after a try block is also called "completion clause" as reaching the `else` clause in a `try` statement means that the try block actually completed successfully.

---

### ▶ Ellipsis *
<!-- Example ID: 969b7100-ab3d-4a7d-ad7d-a6be16181b2b --->
```py
def some_func():
    Ellipsis
```

**Output**
```py
>>> some_func()
# No output, No Error

>>> SomeRandomString
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'SomeRandomString' is not defined

>>> Ellipsis
Ellipsis
```

#### 💡 Explanation
- In Python, `Ellipsis` is a globally available built-in object which is equivalent to `...`.
    ```py
    >>> ...
    Ellipsis
    ```
- Eliipsis can be used for several purposes,
    + As a placeholder for code that hasn't been written yet (just like `pass` statement)
    + In slicing syntax to represent the full slices in remaining direction
    ```py
    >>> import numpy as np
    >>> three_dimensional_array = np.arange(8).reshape(2, 2, 2)
    array([
        [
            [0, 1],
            [2, 3]
        ],

        [
            [4, 5],
            [6, 7]
        ]
    ])
    ```
    So our `three_dimensional_array` is an array of array of arrays. Let's say we want to print the second element (index `1`) of all the innermost arrays, we can use Ellipsis to bypass all the preceding dimensions
    ```py
    >>> three_dimensional_array[:,:,1]
    array([[1, 3],
       [5, 7]])
    >>> three_dimensional_array[..., 1] # using Ellipsis.
    array([[1, 3],
       [5, 7]])
    ```
    Note: this will work for any number of dimensions. You can even select slice in first and last dimension and ignore the middle ones this way (`n_dimensional_array[firs_dim_slice, ..., last_dim_slice]`)
    + In [type hinting](https://docs.python.org/3/library/typing.html) to indicate only a part of the type (like `(Callable[..., int]` or `Tuple[str, ...]`))
    + You may also use Ellipsis as a default function argument (in the cases when you want to differentiate between the "no argument passed" and "None value passed" scenarios).

---

### ▶ Inpinity
<!-- Example ID: ff473ea8-a3b1-4876-a6f0-4378aff790c1 --->
The spelling is intended. Please, don't submit a patch for this.

**Output (Python 3.x):**
```py
>>> infinity = float('infinity')
>>> hash(infinity)
314159
>>> hash(float('-inf'))
-314159
```

#### 💡 Explanation:
- Hash of infinity is 10⁵ x π.
- Interestingly, the hash of `float('-inf')` is "-10⁵ x π" in Python 3, whereas "-10⁵ x e" in Python 2.

---

### ▶ Let's mangle
<!-- Example ID: 37146d2d-9e67-43a9-8729-3c17934b910c --->
1\.
```py
class Yo(object):
    def __init__(self):
        self.__honey = True
        self.bro = True
```

**Output:**
```py
>>> Yo().bro
True
>>> Yo().__honey
AttributeError: 'Yo' object has no attribute '__honey'
>>> Yo()._Yo__honey
True
```

2\.
```py
class Yo(object):
    def __init__(self):
        # Let's try something symmetrical this time
        self.__honey__ = True
        self.bro = True
```

**Output:**
```py
>>> Yo().bro
True

>>> Yo()._Yo__honey__
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Yo' object has no attribute '_Yo__honey__'
```

Why did `Yo()._Yo__honey` work?

3\.

```py
_A__variable = "Some value"

class A(object):
    def some_func(self):
        return __variable # not initiatlized anywhere yet
```

**Output:**
```py
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'A' object has no attribute '__variable'

>>> >>> A().some_func()
'Some value'
```


#### 💡 Explanation:

* [Name Mangling](https://en.wikipedia.org/wiki/Name_mangling) is used to avoid naming collisions between different namespaces.
* In Python, the interpreter modifies (mangles) the class member names starting with `__` (double underscore a.k.a "dunder") and not ending with more than one trailing underscore by adding `_NameOfTheClass` in front.
* So, to access `__honey` attribute in the first snippet, we had to append `_Yo` to the front, which would prevent conflicts with the same name attribute defined in any other class.
* But then why didn't it work in the second snippet? Because name mangling excludes the names ending with double underscores.
* The third snippet was also a consequence of name mangling. The name `__variable` in the statement `return __variable` was mangled to `_A__variable`, which also happens to be the name of the variable we declared in the outer scope.
* Also, if the mangled name is longer than 255 characters, truncation will happen.

---
---

## Section: Appearances are deceptive!

### ▶ Skipping lines?
<!-- Example ID: d50bbde1-fb9d-4735-9633-3444b9d2f417 --->
**Output:**
```py
>>> value = 11
>>> valuе = 32
>>> value
11
```

Wut?

**Note:** The easiest way to reproduce this is to simply copy the statements from the above snippet and paste them into your file/shell.

#### 💡 Explanation

Some non-Western characters look identical to letters in the English alphabet but are considered distinct by the interpreter.

```py
>>> ord('е') # cyrillic 'e' (Ye)
1077
>>> ord('e') # latin 'e', as used in English and typed using standard keyboard
101
>>> 'е' == 'e'
False

>>> value = 42 # latin e
>>> valuе = 23 # cyrillic 'e', Python 2.x interpreter would raise a `SyntaxError` here
>>> value
42
```

The built-in `ord()` function returns a character's Unicode [code point](https://en.wikipedia.org/wiki/Code_point), and different code positions of Cyrillic 'e' and Latin 'e' justify the behavior of the above example.

---

### ▶ Teleportation

<!-- Example ID: edafe923-0c20-4315-b6e1-0c31abfc38f5 --->

```py
# `pip install nump` first.
import numpy as np

def energy_send(x):
    # Initializing a numpy array
    np.array([float(x)])

def energy_receive():
    # Return an empty numpy array
    return np.empty((), dtype=np.float).tolist()
```

**Output:**
```py
>>> energy_send(123.456)
>>> energy_receive()
123.456
```

Where's the Nobel Prize?

#### 💡 Explanation:

* Notice that the numpy array created in the `energy_send` function is not returned, so that memory space is free to reallocate.
* `numpy.empty()` returns the next free memory slot without reinitializing it. This memory spot just happens to be the same one that was just freed (usually, but not always).

---

### ▶ Well, something is fishy...
<!-- Example ID: cb6a37c5-74f7-44ca-b58c-3b902419b362 --->
```py
def square(x):
    """
    A simple function to calculate the square of a number by addition.
    """
    sum_so_far = 0
    for counter in range(x):
        sum_so_far = sum_so_far + x
  return sum_so_far
```

**Output (Python 2.x):**

```py
>>> square(10)
10
```

Shouldn't that be 100?

**Note:** If you're not able to reproduce this, try running the file [mixed_tabs_and_spaces.py](/mixed_tabs_and_spaces.py) via the shell.

#### 💡 Explanation

* **Don't mix tabs and spaces!** The character just preceding return is a "tab",  and the code is indented by multiple of "4 spaces" elsewhere in the example.
* This is how Python handles tabs:
  
  > First, tabs are replaced (from left to right) by one to eight spaces such that the total number of characters up to and including the replacement is a multiple of eight <...>
* So the "tab" at the last line of `square` function is replaced with eight spaces, and it gets into the loop.
* Python 3 is kind enough to throw an error for such cases automatically.

    **Output (Python 3.x):**
    ```py
    TabError: inconsistent use of tabs and spaces in indentation
    ```

---
---

## Section: Miscellaneous


### ▶ `+=` is faster
<!-- Example ID: bfd19c60-a807-4a26-9598-4912b86ddb36 --->

```py
# using "+", three strings:
>>> timeit.timeit("s1 = s1 + s2 + s3", setup="s1 = ' ' * 100000; s2 = ' ' * 100000; s3 = ' ' * 100000", number=100)
0.25748300552368164
# using "+=", three strings:
>>> timeit.timeit("s1 += s2 + s3", setup="s1 = ' ' * 100000; s2 = ' ' * 100000; s3 = ' ' * 100000", number=100)
0.012188911437988281
```

#### 💡 Explanation:
+ `+=` is faster than `+` for concatenating more than two strings because the first string (example, `s1` for `s1 += s2 + s3`) is not destroyed while calculating the complete string.

---

### ▶ Let's make a giant string!
<!-- Example ID: c7a07424-63fe-4504-9842-8f3d334f28fc --->
```py
def add_string_with_plus(iters):
    s = ""
    for i in range(iters):
        s += "xyz"
    assert len(s) == 3*iters

def add_bytes_with_plus(iters):
    s = b""
    for i in range(iters):
        s += b"xyz"
    assert len(s) == 3*iters

def add_string_with_format(iters):
    fs = "{}"*iters
    s = fs.format(*(["xyz"]*iters))
    assert len(s) == 3*iters

def add_string_with_join(iters):
    l = []
    for i in range(iters):
        l.append("xyz")
    s = "".join(l)
    assert len(s) == 3*iters

def convert_list_to_string(l, iters):
    s = "".join(l)
    assert len(s) == 3*iters
```

**Output:**

```py
# Executed in ipython shell using %timeit for better readablity of results.
# You can also use the timeit module in normal python shell/scriptm=, example usage below
# timeit.timeit('add_string_with_plus(10000)', number=1000, globals=globals())

>>> NUM_ITERS = 1000
>>> %timeit -n1000 add_string_with_plus(NUM_ITERS)
124 µs ± 4.73 µs per loop (mean ± std. dev. of 7 runs, 100 loops each)
>>> %timeit -n1000 add_bytes_with_plus(NUM_ITERS)
211 µs ± 10.5 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_format(NUM_ITERS)
61 µs ± 2.18 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_join(NUM_ITERS)
117 µs ± 3.21 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> l = ["xyz"]*NUM_ITERS
>>> %timeit -n1000 convert_list_to_string(l, NUM_ITERS)
10.1 µs ± 1.06 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```

Let's increase the number of iterations by a factor of 10.

```py
>>> NUM_ITERS = 10000
>>> %timeit -n1000 add_string_with_plus(NUM_ITERS) # Linear increase in execution time
1.26 ms ± 76.8 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_bytes_with_plus(NUM_ITERS) # Quadratic increase
6.82 ms ± 134 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_format(NUM_ITERS) # Linear increase
645 µs ± 24.5 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> %timeit -n1000 add_string_with_join(NUM_ITERS) # Linear increase
1.17 ms ± 7.25 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
>>> l = ["xyz"]*NUM_ITERS
>>> %timeit -n1000 convert_list_to_string(l, NUM_ITERS) # Linear increase
86.3 µs ± 2 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```

#### 💡 Explanation
- You can read more about [timeit](https://docs.python.org/3/library/timeit.html) or [%timeit](https://ipython.org/ipython-doc/dev/interactive/magics.html#magic-timeit) on these links. They are used to measure the execution time of code pieces.
- Don't use `+` for generating long strings — In Python, `str` is immutable, so the left and right strings have to be copied into the new string for every pair of concatenations. If you concatenate four strings of length 10, you'll be copying (10+10) + ((10+10)+10) + (((10+10)+10)+10) = 90 characters instead of just 40 characters. Things get quadratically worse as the number and size of the string increases (justified with the execution times of `add_bytes_with_plus` function)
- Therefore, it's advised to use `.format.` or `%` syntax (however, they are slightly slower than `+` for very short strings).
- Or better, if already you've contents available in the form of an iterable object, then use `''.join(iterable_object)` which is much faster.
- Unlike `add_bytes_with_plus` because of the `+=` optimizations discussed in the previous example, `add_string_with_plus` didn't show a quadratic increase in execution time. Had the statement been `s = s + "x" + "y" + "z"` instead of `s += "xyz"`, the increase would have been quadratic.
  ```py
  def add_string_with_plus(iters):
      s = ""
      for i in range(iters):
          s = s + "x" + "y" + "z"
      assert len(s) == 3*iters

  >>> %timeit -n100 add_string_with_plus(1000)
  388 µs ± 22.4 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
  >>> %timeit -n100 add_string_with_plus(10000) # Quadratic increase in execution time
  9 ms ± 298 µs per loop (mean ± std. dev. of 7 runs, 100 loops each)
  ```
- So many ways to format and create a giant string are somewhat in contrast to the [Zen of Python](https://www.python.org/dev/peps/pep-0020/), according to which,
  
    > There should be one-- and preferably only one --obvious way to do it.

---

### ▶ Minor Ones *
<!-- Example ID: f885cb82-f1e4-4daa-9ff3-972b14cb1324 --->
* `join()` is a string operation instead of list operation. (sort of counter-intuitive at first usage)

  **💡 Explanation:** If `join()` is a method on a string, then it can operate on any iterable (list, tuple, iterators). If it were a method on a list, it'd have to be implemented separately by every type. Also, it doesn't make much sense to put a string-specific method on a generic `list` object API.
  
* Few weird looking but semantically correct statements:
  + `[] = ()` is a semantically correct statement (unpacking an empty `tuple` into an empty `list`)
  + `'a'[0][0][0][0][0]` is also a semantically correct statement as strings are [sequences](https://docs.python.org/3/glossary.html#term-sequence)(iterables supporting element access using integer indices) in Python.
  + `3 --0-- 5 == 8` and `--5 == 5` are both semantically correct statements and evaluate to `True`.

* Given that `a` is a number, `++a` and `--a` are both valid Python statements but don't behave the same way as compared with similar statements in languages like C, C++, or Java.
  ```py
  >>> a = 5
  >>> a
  5
  >>> ++a
  5
  >>> --a
  5
  ```

  **💡 Explanation:**
  + There is no `++` operator in Python grammar. It is actually two `+` operators.
  + `++a` parses as `+(+a)` which translates to `a`. Similarly, the output of the statement `--a` can be justified.
  + This StackOverflow [thread](https://stackoverflow.com/questions/3654830/why-are-there-no-and-operators-in-python) discusses the rationale behind the absence of increment and decrement operators in Python.

* You must be aware of the Walrus operator in Python. But have you ever heard about *the space-invader operator*?
  ```py
  >>> a = 42
  >>> a -=- 1
  >>> a
  43
  ```
  It is used as an alternative incrementation operator, together with another one
  ```py
  >>> a +=+ 1
  >>> a
  >>> 44
  ```
  **💡 Explanation:** This prank comes from [Raymond Hettinger's tweet](https://twitter.com/raymondh/status/1131103570856632321?lang=en). The space invader operator is actually just a malformatted `a -= (-1)`. Which is equivalent to `a = a - (- 1)`. Similar for the `a += (+ 1)` case.
  
* Python has an undocumented [converse implication](https://en.wikipedia.org/wiki/Converse_implication) operator. 
     
     ```py
     >>> False ** False == True
     True
     >>> False ** True == False
     True
     >>> True ** False == True
     True
     >>> True ** True == True
     True
     ```

     **💡 Explanation:** If you replace `False` and `True` by 0 and 1 and do the maths, the truth table is equivalent to a converse implication operator. ([Source](https://github.com/cosmologicon/pywat/blob/master/explanation.md#the-undocumented-converse-implication-operator))
     
* Since we are talking operators, there's also `@` operator for matrix multiplication (don't worry, this time it's for real).

     ```py
     >>> import numpy as np
     >>> np.array([2, 2, 2]) @ np.array([7, 8, 8])
     46
     ```

     **💡 Explanation:** The `@` operator was added in Python 3.5 keeping sthe cientific community in mind. Any object can overload `__matmul__` magic method to define behavior for this operator.

* From Python 3.8 onwards you can use a typical f-string syntax like `f'{some_var=}` for quick debugging. Example,
    ```py
    >>> some_string = "wtfpython"
    >>> f'{some_string=}'
    "string='wtfpython'"
    ``` 

* Python uses 2 bytes for local variable storage in functions. In theory, this means that only 65536 variables can be defined in a function. However, python has a handy solution built in that can be used to store more than 2^16 variable names. The following code demonstrates what happens in the stack when more than 65536 local variables are defined (Warning: This code prints around 2^18 lines of text, so be prepared!):
     
     ```py
     import dis
    exec("""
    def f():
        """ + """
        """.join(["X" + str(x) + "=" + str(x) for x in range(65539)]))

    f()

    print(dis.dis(f))
    ```
     
* Multiple Python threads won't run your *Python code* concurrently (yes, you heard it right!). It may seem intuitive to spawn several threads and let them execute your Python code concurrently, but, because of the [Global Interpreter Lock](https://wiki.python.org/moin/GlobalInterpreterLock) in Python, all you're doing is making your threads execute on the same core turn by turn. Python threads are good for IO-bound tasks, but to achieve actual parallelization in Python for CPU-bound tasks, you might want to use the Python [multiprocessing](https://docs.python.org/2/library/multiprocessing.html) module.

* Sometimes, the `print` method might not print values immediately. For example,

     ```py
     # File some_file.py
     import time
     
     print("wtfpython", end="_")
     time.sleep(3)
     ```

     This will print the `wtfpython` after 10 seconds due to the `end` argument because the output buffer is flushed either after encountering `\n` or when the program finishes execution. We can force the buffer to flush by passing `flush=True` argument.

* List slicing with out of the bounds indices throws no errors
  ```py
  >>> some_list = [1, 2, 3, 4, 5]
  >>> some_list[111:]
  []
  ```

* Slicing an iterable not always creates a new object. For example,
    ```py
    >>> some_str = "wtfpython"
    >>> some_list = ['w', 't', 'f', 'p', 'y', 't', 'h', 'o', 'n']
    >>> some_list is some_list[:] # False expected because a new object is created.
    False
    >>> some_str is some_str[:] # True because strings are immutable, so making a new object is of not much use.
    True
    ```

* `int('١٢٣٤٥٦٧٨٩')` returns `123456789` in Python 3. In Python, Decimal characters include digit characters, and all characters that can be used to form decimal-radix numbers, e.g. U+0660, ARABIC-INDIC DIGIT ZERO. Here's an [interesting story](http://chris.improbable.org/2014/8/25/adventures-in-unicode-digits/) related to this behavior of Python.

* You can seperate numeric literals with underscores (for better readablity) from Python 3 onwards.

     ```py
     >>> six_million = 6_000_000
     >>> six_million
     6000000
     >>> hex_address = 0xF00D_CAFE
     >>> hex_address
     4027435774
     ```

* `'abc'.count('') == 4`. Here's an approximate implementation of `count` method, which would make the things more clear
  ```py
  def count(s, sub):
      result = 0
      for i in range(len(s) + 1 - len(sub)):
          result += (s[i:i + len(sub)] == sub)
      return result
  ```
  The behavior is due to the matching of empty substring(`''`) with slices of length 0 in the original string.

**That's all folks!**

---
---

# 기여하기

wtfpython에 기여할 수 있는 몇 가지 방법이 있어요,

- 새로운 예제들 추천
- 번역 돕기 ([issues labeled translation](https://github.com/satwikkansal/wtfpython/issues?q=is%3Aissue+is%3Aopen+label%3Atranslation) 을 보세요.)
- 오래된 정보, 오타, 서식 오류 등의 작은 수정들
- 차이점들 식별 (불충분한 설명, 중복된 예제 등등.)
- 이 프로젝트를 더욱 재미있고 유용하게 만들기 위한 창의적인 제안들

더 많은 정보들은 [CONTRIBUTING.md](/CONTRIBUTING.md) 을 보세요. 자유롭게 새로운 [issue](https://github.com/satwikkansal/wtfpython/issues/new) 를 만들어 토론해보세요.

추신: 역링크 요청으로 연락하지 마세요. 프로젝트와 관련이 높지 않으면 링크를 추가하지 않습니다.

# 감사의 말

이 항목들의 아이디어와 디자인은 Denys Dovhan's 의 멋진 프로젝트 [wtfjs](https://github.com/denysdovhan/wtfjs) 에서 영감을 받았습니다. Pythonista들의 압도적인 지지는 그것의 현재의 모습을 주었습니다. 

#### 몇개의 멋진 링크들!
* https://www.youtube.com/watch?v=sH4XF6pKKmk
* https://www.reddit.com/r/Python/comments/3cu6ej/what_are_some_wtf_things_about_python
* https://sopython.com/wiki/Common_Gotchas_In_Python
* https://stackoverflow.com/questions/530530/python-2-x-gotchas-and-landmines
* https://stackoverflow.com/questions/1011431/common-pitfalls-in-python
* https://www.python.org/doc/humor/
* https://github.com/cosmologicon/pywat#the-undocumented-converse-implication-operator
* https://www.codementor.io/satwikkansal/python-practices-for-efficient-code-performance-memory-and-usability-aze6oiq65
* https://github.com/wemake-services/wemake-python-styleguide/search?q=wtfpython&type=Issues

# 🎓 License

[![WTFPL 2.0][license-image]][license-url]

&copy; [Satwik Kansal](https://satwikkansal.xyz)

[license-url]: http://www.wtfpl.net
[license-image]: https://img.shields.io/badge/License-WTFPL%202.0-lightgrey.svg?style=flat-square

## 친구들을 놀래켜보세요!

만약 wtfpython이 마음에 드셧다면, 친구들에게 빠르게 공유하기 위한 퀵 링크들을 사용할 수 있어요.

[Twitter](https://twitter.com/intent/tweet?url=https://github.com/buttercrab/wtfpython-ko&text=If%20you%20really%20think%20you%20know%20Python,%20think%20once%20more!%20Check%20out%20wtfpython&hastags=python,wtfpython) | [Linkedin](https://www.linkedin.com/shareArticle?url=https://github.com/buttercrab&title=What%20the%20f*ck%20Python!&summary=If%20you%20really%20thing%20you%20know%20Python,%20think%20once%20more!) | [Facebook](https://www.facebook.com/dialog/share?app_id=536779657179021&display=page&href=https%3A%2F%2Fgithub.com%2Fbuttercrab%2Fwtfpython-ko&quote=If%20you%20really%20think%20you%20know%20Python%2C%20think%20once%20more!)  

## 비슷한 것들을 찾고 있나요?

만약 이것과 비슷한 내용들에 대해 흥미를 느낀다면, 여러분의 이메일을 공유할 수 있어요.
*추신: 각주로, 저에게 [밥을 사주는 것을 고려하거나](https://ko-fi.com/satwikkansal) 또는 [나무를 심는것을 고려해보세요](https://teamtrees.org/).*
