# 크롤링 하기(JSON)



api를 사용하는 경우 해당 api에 맞는 key값 필수 



url = '' <- api 입력



```python
# json 형식으로 추출
json_dict = requests.get(url).json()

변수명 = json_dict.get('원하는 정보')

For 문으로 여러 개의 데이터


# json.dump / json으로 데이터 저장하기

리스트명 = []
리스트명.append(변수명)

# 상세히 추가하기

book = dict()
book["title"] = 변수명['title']

리스트명.append(book)

with open('./bookinfo2.json', 'w', encoding="utf-8") as make_file:
    json.dump(리스트명, make_file, ensure_ascii=False, indent="\t")
```

 





