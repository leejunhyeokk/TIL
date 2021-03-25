맛집

메뉴들

- 메뉴1

- - 맛있는거
- - 재료 
- - - 재료1
  - - 재료 2

# XML

```html
HTML과 유사
요구사항에 따른 문서를 엄격히 검증 -> 안정성 Good
JSON에 밀리고 있다.

<tag></tag> 내부에 데이터 적용

<shop>
    <name> 맛집 </name>
	<menus>
    	<menu>
        	<name> 맛있는거 </name>
            <ingredients>
                <ingredient> 재료1 </ingredient>
                <ingredient> 재료2 </ingredient>
            </ingredients>
        </menu>
    </menus>
</shop>
```





# JSON

```
편리성이 좋다 -> 가볍다
문법 오류에 취약

{
	"name" : "맛집"
	"menus": [
        {
            "name": "맛잇는거"
            "ingredients": ["재료1", "재료2"]
        }
    ]
}
```





# YAML

```
사람이 보기 좋게 작성
상속을 통해 쓰기 쉽다 -> 편의성
띄어쓰기, 줄맞춤 중요

name: 맛집
menus: 
	- name: 맛있는거
	- ingredients:
		- 재료1
		- 재료2
```

