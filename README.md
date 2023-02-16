# NICE 본인인증 API
NICE 본인인증 API

NICE 본인인증 API를 무료 제공합니다.


![image](https://user-images.githubusercontent.com/79750848/219369852-c5424576-67ed-48d4-ae34-1e9e6310ee34.png)

개인정보 수집을 일절 하지 않으며,<br>
데이터 베이스 테이블이 수집하는 데이터는<br>
API KEY, 생성자, 생성일자, 총 요청 횟수를 수집합니다.

모든 요청은 json 요청으로 받습니다. (application/json)

 # Code
 
 ![image](https://user-images.githubusercontent.com/79750848/219379607-ff6a3bfd-33f1-40fc-96f7-729f764d5f39.png)
 
 ```python
import requests
import base64
from PIL import Image
from io import BytesIO


first = requests.post('http://localhost/send', json={'co' : 'KT'})
 
print( first.json() )
 
#{'image': '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',
#'success': True,
#'taskID': '909074c4-ca5e-4c31-898e-d9e9c2caab11'}


im = Image.open(BytesIO(base64.b64decode(first.json()['image'])))

im.show()

# https://user-images.githubusercontent.com/79750848/219383868-fbf84e75-66be-4dab-82fe-3832825e420b.png

second = requests.post('http://localhost/solve', json={'name' : '홍길동',
                                                       'mynum1': '880101', 
                                                       'mynum2' : '1',
                                                       'econum': '01012345678',
                                                       'task': first.json()['taskID'],
                                                       'text': '897613'}) # text: 위 캡차에 쓰여져 있는 번호
                                                       
print( second.json() )

#{'success': True, 'taskID': '909074c4-ca5e-4c31-898e-d9e9c2caab11'}

# https://user-images.githubusercontent.com/79750848/219382933-57dd9719-cd57-43ec-a125-ac9596bfe281.png

third = requests.post('http://localhost/finish', json={
                                                       'task': first.json()['taskID'],
                                                       'authnumber': '765346'}) #authnumber: 입력한 휴대폰 번호로 간 인증번호



print( third.json() )

# {'auth': True, 'success': True}

 ```
 
# REST API

## Get Captcha Image
### Request

`POST /send/`

    curl -i -H 'Accept: application/json' -d 'co=KT' https://xates.dev:8080/send

##### Parameters
- `co` : your Mobile carrier

### Response

   ```javascript
   {'image': 'iVBORw0KGgoAAAANSUhEUgAAAJYAAAAoCAYAAAAcwQPnAAAHJ0lEQVR42u1cf0hdVRy/mZg4SZZJtX4YK8RsydiQMBmyWDashowtiRAhYsUwG1KsVcNarMYaJf5RLLfELVfJsFVig1FjbP3UHmu5sbZZiKkbkdjLmYmbfQ9+Hl0u53veuefd+3x33A98mLx3zrnnnPs93/M9n+95s6wQQcANxHXEduJx4jhxijhJHCMeIr5FXHalDDiTWIsB9xMnMGDx7wliG/FhzbYqiK3E0452IsR3NCZtxiPKsJzYTDxCjKJvgheIB4hNxNXEPJfzV0DcDGORoZR4kDjtov9i3ks8er9pxGuTbVTriX9oDva0wjCKMbE67fQSFyXRsKrQ90QNkzOmePVMxyCMfhUxnZhLvIO4lHg/FsATxAbiFiwY4QA+xcL5iThA/It4GR4xKcjAKjUZcLWjrRXwSm7aEOUrfTasTHhhrzweZ0x+GZaXvAzP5TvaE+ikiAmK0E4hthXTdu716SVkYuUm6vGEMb1K7NOs9wXxG+Ip4rDBgvOL08nYDiskDz4It5tp25cXE3czHW1FuaPM94dhNGngWuKQpFw/vKfXhrVf8d0xBMn1xBeJbxL3Yiy/Ei8Sf0HsNZMi/BN9E7HqV8RO4vsYxxvE92DU54iX5sqwOiUPTleUb5SUHyWWMZPQ5zCWGPIZ79agePZVmJDbiPcgxnuEWEN8BlvTCUd70RQyiFisJOLYs8QenP6E4e8i7iC+TKwjvqCob0cODlM7EK9Oa3irHuwuvkI28ZvinBplg21mBlLrqHsX8XZ4wFZJ+TF8/gk8XQSrc5RZfXPFSzCQiKKMiBvvQ6iwgDjP5buRtfmPoSEJT/xQMk+E00xnypjy6Ywx9DID+wjbSioZxd+Ie0T8003cB/lDbCMbiU/hUPIgtnCxum/EIozJLWkaW3aisgAXeKekITkxxHRwlNFOnpOU/V1jwF4axSDxZxjs58QPiCcd5bYwcZEIoLMTeNluTnomiG1t+1wE4ilhSE5sV3RauN2PiR3o/JhHW8ggjuncSe17aDNCo1lCXEi8jng1M4YVjvpN8DSyttt8mMNEDCsnKFubW8zHi/bLw4hA9AHEVNc4np2nEE11kYXTpF24zUScqKO7Jduw3BpSjBchYKesIXFi37CB0XyHU1wVAmxZmSrFc59m6owl4HFL8XkH03aRbVsTubouW0onCqG4xkPDMjUkp1xza5CTopOaAx2E/mVHC1P2CPM84a1GFGKpDood9Vps33GntXTIFP0aqaabEzQsU0OK8UviSusKwALoKPEGvEFSd1kcgbLQdqqsRu5KFUfoIOLQq3Jt340zbde7eLEDVvwkdI6B6t2jWbYfomdh0A1rvYsAvcvxIi185kVcpuOx6uJob1Me9aXbp2DbbT92Ix4OFLIssyT0b8Q7HdvbgIv6G5jPx+P0N8+xAEZs6SeddNAAvGaGLcbsUJR/3jBGUp3aTIxceLCbgmJUGcyxX7y4cms26aoa7AXIATGIgX+rMUHleLbs++Nx+tyqkSngPNYI4kkZDltmCd1Edax0LFAhsey01FeXIkExrJ3MZJXbyqyMk3M7I/EYj8ELRtHeBLaVddb/ucgipr0ORX8XS9JJ8zVTVTPY7p3erxYe6ZyhIOm18p7NvJcYa1LdqDgR8aREcyqBGs8N9iWD51cbtOX0rh8y5bgU01acHoVU8q8LUVclSPqR0lFJJvtT3bBU97B+IN7iKF+mcP19Bs9vY9oqZcovZ3QyoUnlQ6l/0prN+bmJ9XRuJPilvKuwlGk3muqGNaoRPzmvHzcaTr7M3Y8zGpkM8yTalMhPnnXheTiK+u/CI5m8SL8My/JorpOOaUXH7X/X2erkWvz1YjfYyrTTghjiFeIe4tfE8x56nz2Is0TcKG4vXO+It7jc5VwYVrpHc510RBVxyHmJsYmbEKeYOsNI74it6FG8NLGl3Y10RA4C/AIc373OSYrT3jEYTiOMU3Zzo1ExHzVM201zZFiPB/VkeEDxkpYgzppJYb5tzf7CJ4sZXwOzreUzsgt3l73MQ8MSh49KjXdTYPEpr22pblir43iAZz1UsHU4iqO8uKrzOryfCNjXWPwNzXganSwnOIQTaewOfolCwzpqGAfF+5WOOFxsh4ofE2rTELC/ZvEpqUlmYaQcuj0wiF2IiUzr/2jN3tDksJmpt1BTUpk07FcUniMRtdxr1gdFIM02VJxjQeTaBCe+XSKuOtHJ1M3QHGOlZfZbxwoP0jBecpMVQGy03P2iRfxErDCBiRcX8lZp9q3fg+B4kUI0lf2kvdjFlueWh1yWjyi0vUAgCyej2H9UMQFJQsRZInfYhVNVEVM/F3GbOEV9Zs3mvKbQRhTxSrMjXaSDCQ9PXeVIl/Ta2p2Coe+VeCk/DMtCnFQPdf2Mba4nbXO9LegGFSJEiBAhQoQIESJEiBAhQoQIESJEiBAhQoTg8B8N+FwqTTm1fAAAAABJRU5ErkJggg==',
 'success': True,
 'taskID': '909074c4-ca5e-4c31-898e-d9e9c2caab11'
 }
 ``` 
<br>
 #### Get Image
 
 ```python
import base64
from PIL import Image
from io import BytesIO

data = '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'
#Image Data that be encoded as Base64 (Get Captcha Image Response data)

im = Image.open(BytesIO(base64.b64decode(data)))
#im.save('captcha.jpg')
im.show()
```

#### Output
 ![image](https://user-images.githubusercontent.com/79750848/219375570-81cccf55-3a82-41d9-9e20-6130ffe0fe3a.png)
 
 ## Solve Captcha Task
### Request

`POST /solve/`

    curl -i -H 'Accept: application/json' -d 'name=홍길동&mynum1=880101&mynum2=1&econum=01012345678&task=909074c4-ca5e-4c31-898e-d9e9c2caab11&text=897613' https://xates.dev:8080/solve
    
##### Parameters
- `name` : your name
- `mynum1` : your birth date
- `mynum2` : your resident registration number
- `econum` : your phone number
- `task` : your taskID
- `text` : auth numbers of above captcha image

### Response

   ```javascript
{'success': True,
'taskID': '909074c4-ca5e-4c31-898e-d9e9c2caab11'}
 ```
 
 ## Submit Auth Number
### Request

`POST /finish/`

    curl -i -H 'Accept: application/json' -d 'task=909074c4-ca5e-4c31-898e-d9e9c2caab11&authnumber=765346' https://xates.dev:8080/finish

##### Parameters
- `task` : your taskID
- `authnumber` : authnumber you received

##### Example
![image](https://user-images.githubusercontent.com/79750848/219382933-57dd9719-cd57-43ec-a125-ac9596bfe281.png)

### Response

   ```javascript
{'auth': True, 'success': True}
 ``` 
 
 # 한국어

## 캡차 이미지 얻기
### 요청

`POST /send/`

    curl -i -H 'Accept: application/json' -d 'co=KT' https://xates.dev:8080/send

##### 요청 양식
- `co` : 통신사

### Response

   ```javascript
   {'image': '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',
 'success': True,
 'taskID': '909074c4-ca5e-4c31-898e-d9e9c2caab11'
 }
 ``` 
<br>
 #### 이미지 얻기
 
 ```python
import base64
from PIL import Image
from io import BytesIO

data = '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'
#캡차 이미지 얻기에서 반환된 'image' 키의 데이터

im = Image.open(BytesIO(base64.b64decode(data)))
#im.save('captcha.jpg')
im.show()
```

#### 출력
 ![image](https://user-images.githubusercontent.com/79750848/219375570-81cccf55-3a82-41d9-9e20-6130ffe0fe3a.png)
 
 ## 캡차 풀기
### 요청

`POST /solve/`

    curl -i -H 'Accept: application/json' -d 'name=홍길동&mynum1=880101&mynum2=1&econum=01012345678&task=909074c4-ca5e-4c31-898e-d9e9c2caab11&text=897613' https://xates.dev:8080/solve
    
##### 요청 양식
- `name` : 이름
- `mynum1` : 생년월일
- `mynum2` : 주민등록번호
- `econum` : 핸드폰 번호
- `task` : taskID
- `text` : 위 캡차 이미지의 인증번호

### 응답

  ```javascript
{'success': True,
'taskID': '909074c4-ca5e-4c31-898e-d9e9c2caab11'}
 ```
 
 ## 인증번호 제출
### 요청

`POST /finish/`

    curl -i -H 'Accept: application/json' -d 'task=909074c4-ca5e-4c31-898e-d9e9c2caab11&authnumber=765346' https://xates.dev:8080/finish

##### 요청 양식
- `task` : taskID
- `authnumber` : 핸드폰으로 받은 인증번호

##### Example
![image](https://user-images.githubusercontent.com/79750848/219382933-57dd9719-cd57-43ec-a125-ac9596bfe281.png)


### 응답

   ```javascript
{'auth': True, 'success': True}
