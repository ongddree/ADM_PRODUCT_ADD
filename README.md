# 상품 등록 관리 페이지

## 프로젝트 소개

상품 등록 어드민 페이지

## 팀원 소개

🏃‍ [박서영](https://github.com/ongddree) (팀장) <br/>
🏃‍ 양다혜 <br/>
🏃‍ 박서윤 <br/>
🏃‍ 민지연 <br/>

## 배포 주소

[배포 사이트 바로가기](https://brave-visvesvaraya-053de0.netlify.app/)

## 설치 및 시작하는 법

**프로젝트 클론**

```
$ git clone https://github.com/On-Basic/ADM_PRODUCT_ADD.git
```

**패키지 설치**

```
$ yarn
```

**서버 실행**

```
$ yarn start
```


## 과제 구현 목록

### 상품 옵션

#### 박서영

☑️ 옵션은 옵션 세트 추가를 통해 등록할 수 있음

☑️ 옵션 세트 및 옵션 세트 내 옵션은 여러 개 생성할 수 있음

☑️ 옵션 세트 내 이미지는 1개만 지정 가능하며, 옵션은 여러 개 생성할 수 있음

☑️ 관리자는 해당 옵션에 추가 옵션 상품을 등록할 수 있음

☑️ 옵션 1개당 여러개의 추가 옵션 상품을 등록할 수 있음

☑️ [추가 옵션 상품 등록] 버튼 TAP 시, 추가옵션 등록 SELL 추가됨

☑️ 상품 정상가 : 상품의 정상가를 입력할 수 있음

☑️ 상품 판매가 : 상품의 판매가를 입력할 수 있음

<br/>
<br/>

### 공통 컴포넌트

#### 박서영

☑️ ContentWrap : 기능별 섹션 레이아웃

☑️ Button : font-color, background, border, text 등 인자를 받아 커스텀할 수 있는 버튼 컴포넌트

☑️ Input : width, text, desc 등 인자를 받아 커스텀할 수 있는 Input 컴포넌트

<br/>

## 기능별 영상

### 상품 옵션

#### 박서영

- 옵션 세트 추가 <br/> <br/>
  ![옵션세트추가](https://user-images.githubusercontent.com/93420227/151652844-b57c1b8a-1bdf-405a-977d-3b7f7e4b7b90.gif)
- 옵션 세트 내 옵션 추가 <br/> <br/>
  ![옵션세트내옵션추가](https://user-images.githubusercontent.com/93420227/151652835-69846b15-8f79-4461-a56c-4ffb39dcbc50.gif)
- 추가 옵션 추가 <br/> <br/>
  ![추가옵션등록](https://user-images.githubusercontent.com/93420227/151652854-8cda92c2-0287-4e81-bf09-795a90e400d9.gif)
- 이미지 프리뷰 첨부 <br/> <br/>
  ![이미지첨부](https://user-images.githubusercontent.com/93420227/151652847-52a1969d-4eae-48d3-9679-2fbc334518a8.gif)


## 과제 후기

### 🙋‍♀️ 박서영

테스크 분석 및 분리, 공용 컴포넌트 제작, 깃헙 이슈를 통한 프로젝트 관리, 데이터 명세 등 사전에 충분한 협의를 통해 체계적으로 계획을 세웠던 프로젝트였다. 불필요하게 낭비되는 코드를 줄이고 건설적으로 코드를 설계할 수 있어서 공부가 많이 되었다.



## 프로젝트 구조 설명

```bash
.
├── App.css
├── App.js
├── components
│   ├── common
│   │   ├── Button.jsx
│   │   ├── Input.jsx
│   │   ├── InsertImage.jsx
│   │   ├── InsertImagePreview.jsx
│   │   ├── Radio.jsx
│   │   ├── Toggle.jsx
│   │   ├── datepicker
│   │   └── index.js
│   ├── infoNotice
│   │   ├── InfoNotice.jsx
│   │   └── infoNoticeForm
│   ├── layout
│   │   ├── Contentwrap.jsx
│   │   ├── navbar
│   │   └── sidebar
│   ├── productExpoSalesPeriod
│   │   ├── ExposurePeriodSet.jsx
│   │   └── SalesPeriodSet.jsx
│   ├── productInfo
│   │   └── ProductInfo.jsx
│   ├── productOrderSet
│   │   ├── ProductOrderStart.jsx
│   │   └── ProductPickUp.jsx
│   ├── productPreOrderReservation
│   │   └── PreOrderReservetionSet.jsx
│   └── productoption
│       ├── Optionset.jsx
│       ├── Suboption.jsx
│       └── index.js
├── hooks
│   ├── SubmitForm.jsx
│   ├── useForm.js
│   └── validate.js
├── index.css
├── index.js
├── logo.svg
├── pages
│   ├── admin.jsx
│   └── adminSection
│       ├── ExpoSalesPeriodSet.jsx
│       ├── addoption.jsx
│       ├── pagesInfoNotice.jsx
│       ├── productInfo.jsx
│       └── productorder.jsx
└── style
    ├── globalstyle.js
    └── theme.js


```

### 데이터 post 명세

```
{
  "product": {
      "exposuredeadline": String,
      "salesdeadline": String,
      "categories": Array<string>,
      "filtertags": Array<string>,
      "title": String,
      "desc": String,
      "code": String,
      "thumbnamil" : String,
      "representativeimages": Array<string>,
      "stock": Number,
      "option + ${index}": {
              "image": String,
              "optiontit": String,
              "regularprice" : Number,
              "sellingprice" : Number,
              "stock" : String,
              "taxation" : String,
              "addoption + ${index}": {
                  "optiontit" : String,
                  "regularprice" : Number
                  }
        }
      "introimages": Array<string>,
      "recommandedimages": Array<string>,
      "informationnotice" : {
          "productname": String,
          "origin": String,
          "ranking" : String,
          "custody" : String,
          "foodcode" : String,
          "key" : String,
        }
    "deliverydesignation" : String,
    "pickup" : String,
    "preorderdelivery" : String,
    "mileage" : String,
    "thankyoucard" : String
		}
}
```

<br/>
