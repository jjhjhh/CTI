## YaraRule 개요

악성코드의 시그니쳐를 이용해서 악성 코드의 종류들을 식별하고 분류하는 목적으로 사용하는 도구

<br>

## YaraRule 실습

설치 : https://github.com/virustotal/yara/releases

파일배치는 아래와 같다

```bash
(yara-4.3.2-2150-win64)
├── 01.rule
├── sample
│   ├── sample.txt
│   └── sample2.txt
├── yara64.exe
└── yarac64.exe
```

<br>

[01.rule]

```jsx
/* TEST */
rule example
{
        strings:
                $a = "autorun" wide
                $h = {30 AA AA BB 10}
                $b = "Software"
                $c = "sometimes"
        condition:
               any of them
}
```

<br>

텍스트 파일에서 strings에 있는 문자가 있는 부분을 추출하겠다는 뜻이다 

📝🌱👍 

- **hex**
    
    `$a = {aa bb c? dd ??}`  → ?는 바뀌는 값이라는 뜻. 와일드카드
    
    `$b = {4D [2-8] 00 11 22}` → 2-8바이트 사이의 값을 가질 수 있음  (4D AA 00 11 22) (4D AA BB 00 11 22)
    
    그러나 시작 부분은 정확하게 지정해줘야함 → `$d = {**~~4?~~** [2] 00 11 22}`
    
    범위에 `-`만 넣으면 무한대라는 뜻 → `$e = {4D [2-5] [-] 11 22}` 
    
    (응용예시) `$c = {4D [2-255] 00 ?? 22}`
    
- **정규식**
    
    `$r = /md5: [0-9a-ZA-Z]{32}/` → 정규식 검색 가능 
    
- **수식어**
    
    "autorun" nocase ⇒ 대소문자 구분X 검색. 느림
    
    “autorun” wide ⇒ 유니코드값 검색 
    
    “autorun” fullword ⇒ 해당 단어가 포함된 단어들만 검색 

<br>

실행명령 : `yara64.exe -s 01.rule sample` 

<br>

결과 : 

```jsx
yara-4.3.2-2150-win64>yara64.exe -s 01.rule sample
malware_214 sample\sample2.txt
0x485:$c: sometimes
0x49c:$c: sometimes
malware_214 sample\sample.txt
0x71:$b: Software
0x70c:$b: Software
0x1952:$b: Software
0x196b:$b: Software
0xd49:$c: sometimes
```
