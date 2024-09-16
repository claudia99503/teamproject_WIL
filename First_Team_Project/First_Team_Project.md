# First Team Project ( 2024-08-13 ~ 2024-09-02 )

## 1. 서비스 소개

이번 프로젝트에서는 **'View My Startup'** 이라는 서비스를 개발했습니다. 이 서비스는 개인 투자자들이 스타트업 정보를 쉽게 확인하고, 가상 투자 및 기업 간 비교를 통해 투자 결정을 모의 체험할 수 있는 기능을 제공합니다.

![9F90073A-3F89-4AF6-8A8B-52388088CDFC](https://github.com/user-attachments/assets/f0a17654-554e-4f4c-bc4f-c6a2d111df73)

<b>[View My Startup 바로가기](https://team4-vms.netlify.app/)</b> <br>
<b>[View My Startup_ReadMe](https://github.com/ViewMyStartup/view-my-startup)<b>

### 구현된 주요 기능:
- **스타트업 정보 조회**: 투자 금액, 매출액, 고용 인원을 포함한 기업 정보를 비교할 수 있습니다.
- **기업 간 비교**: 최대 5개의 기업을 선택하여 상세한 비교 결과를 확인할 수 있습니다.
- **가상 투자**: 원하는 스타트업에 가상으로 투자하고, 투자 내역을 관리할 수 있습니다.
- **순위 및 선택 현황 조회**: 각 기업의 투자 순위 및 선택된 횟수를 조회할 수 있습니다.
- **투자 내역 수정 및 삭제**: 투자 내역을 수정하거나 삭제할 수 있는 기능을 제공합니다.

---

<br>

## 2. 기술 및 개발 환경

프로젝트는 다음과 같은 기술 스택과 협업 도구를 사용했습니다:

### Frontend
- React
- JavaScript
- CSS

### Backend
- Node.js
- Express
- Prisma

### Database
- PostgreSQL

### Design
- Figma

### 협업 도구 및 배포
- Git, GitHub, Notion, Discord
- 배포는 Netlify와 Render를 사용하여 진행

---

<br>

## 3. 개발 일정 (2024-08-13 ~ 2024-09-02)

### 1. 기획 완료

- [x] 요구사항 분석 및 수집
- [x] 기술 스택 검토 및 선정
- [x] GitBranch 전략 수립
- [x] PR 규칙 등 팀 컨벤션 확립 [**2024-08-13 ~ 2024-08-14**]

### 2. 프론트엔드 개발

- [x] 각 단위별 담당자 지정 [**2024-08-13**]
- [x] 최소 단위 컴포넌트 개발 (Component 1) [**2024-08-14 ~ 2024-08-16**]
- [x] 중간 단위 컴포넌트 개발 (Component 2) [**2024-08-17 ~ 2024-08-19**]
- [x] 페이지 단위 컴포넌트 개발 [**2024-08-20 ~ 2024-08-22**]

### 3. 프론트엔드 개발 마무리, 중간 점검 및 중간 발표

- [x] 중간발표 [**2024-08-22**]
- [x] 백엔드 API 구성, 담당자 지정 및 DB 구축 [**2024-08-22**]
- [x] 중간 회의

### 4. 백엔드 개발 및 프론트엔드 통합 과정

- [x] 백엔드 API 구현 [**2024-08-23**]
- [x] 백엔드 - 프론트엔드 통합 및 디테일 수정, 프로젝트 마무리 단계 [**2024-08-25** ~ **2024-08-29**]
- [x] 단위 테스트 수행 [**2024-08-30**]

### 5. 릴리스

- [x] 최종 검토
- [x] **최종 발표** [**2024-09-02**]

---

<br>

## 4. 팀 프로젝트에서 내가 구현한 기능

### 공통 컴포넌트

- TextareaBar
- Dropdown
- DropdownSmallSize
- AddCompanyBtn
- CompareCompanyBtn
- CompareOtherCompanyBtn
- ResetBtn
- ModalPassword

### 프론트엔드

- 나의 기업 비교 페이지 구현
- 기업 비교 API를 호출하여 나의 기업과 선택한 기업의 비교 결과를 화면에 렌더링
  - **비교 결과 확인하기 섹션**: 나의 기업과 선택한 기업 간의 비교 결과를 화면에 렌더링
  - **기업 순위 확인하기 섹션**: 나의 기업과 전체 기업에서 나의 기업을 제외한 후, 나의 기업과 근접한 위 2개, 아래 2개 기업을 조회하여 순위와 함께 렌더링 <br> (나의 기업이 상위 또는 하위에 있을 경우, 나의 기업 포함 5개 기업 조회)
    - 나의 기업의 순위를 계산하고, 근접한 상위 및 하위 기업들과 함께 순위를 반환하는 기능을 구현하여, 이를 바탕으로 나의 기업비교 페이지에서 순위와 비교 결과를 화면에 렌더링

### 백엔드

- 기업 리스트 조회 API (GET /api/companies) 구현
  - **페이지네이션 기능**: 클라이언트 요청에 따라 `page`와 `limit` 값을 활용해 결과를 페이지 단위로 분할하여 반환
  - **검색 기능**: 기업명 또는 카테고리에 대한 부분 일치 검색을 가능하게 하며, 대소문자 구분 없이 검색 실행
  - **정렬 기능**: `sort_by`와 `order` 매개변수를 사용해 원하는 필드와 정렬 순서(오름차순/내림차순)로 결과를 정렬하여 반환
  - **필터링 및 카운팅**: 검색 조건에 따른 기업 목록을 필터링하고, 해당 조건에 맞는 총 기업 수를 함께 반환하여 클라이언트가 전체 결과를 쉽게 파악할 수 있도록 구현
  - **에러 처리**: API 호출 중 발생할 수 있는 서버 측 오류를 처리하고, 사용자에게 적절한 오류 메시지를 반환하도록 구현

<br>

### **나의 기업 비교 페이지**

<table>
  <tr>
    <th style="width: 650px; height: 100px;">데스크탑 & 태블릿 버전</th>
    <th style="width: 350px; height: 100px;">모바일 버전</th>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/049f2563-d5c6-4e3e-963f-a813b6338d0d" alt="데스크탑 & 태블릿 버전 이미지"></td>
    <td><img src="https://github.com/user-attachments/assets/6f3b2013-9342-4a1e-85a8-7014b4e0f5f8" alt="모바일 버전 이미지"></td>
  </tr>
</table>

- **비교할 기업 선택**
  - 나의 기업 및 비교 대상 기업(최대 5개)를 선택합니다
  - 나의 기업 선택 시, 페이지네이션, 기업명 검색 기능, 최근 선택된 기업 조회(최대 5개)를 제공합니다. 또한 선택 횟수가 누적됩니다
  - 비교 대상 기업 선택 시, 최대 5개까지 가능하며, 페이지네이션, 기업명 검색 기능, 선택한 기업 목록을 제공을 제공하고, 선택 횟수가 누적됩니다. 선택 완료 버튼을 클릭해야 선택이 완료되며 1개 이상 5개 이하일 경우에만 활성화됩니다
  - 선택 취소 및 전체 선택 초기화 기능을 제공합니다
- **기업 비교 결과 확인 (나의 기업 vs 비교 대상 선택 기업)**
  - 내 기업과 비교 대상 기업들 비교 결과 조회 가능합니다. 기업명, 기업 소개, 카테고리, 누적 투자 금액, 매출액, 고용 인원이 조회됩니다
  - 누적 투자 금액, 매출액, 고용 인원 별 오름차순/내림차순 정렬을 제공합니다
- **나의 기업 순위 확인 (나의 기업 vs 전체 기업)**
  - 나의 기업으로 선택한 기업의 매출액, 고용 인원 별 오름차순/내림차순 기준 순위 조회가 가능합니다. 기업명, 기업 소개, 카테고리, 누적 투자 금액, 매출액, 고용 인원이 조회됩니다
  - 나의 기업의 순위와 근접한 위 2개, 아래 2개 기업의 기업명, 기업 소개, 카테고리, 누적 투자 금액, 매출액, 고용 인원이 조회됩니다
  - 다만 나의 기업의 순위가 중간 순위가 아닐(ex. 2위) 경우 나의 기업 포함해서 5개의 기업이 조회됩니다
- **나의 기업에 가상 투자 하기**
  - 비교 결과 조회 페이지에서 나의 기업에 가상 투자하기 버튼을 클릭하면 나의 기업 상세페이지로 이동을 하여 나의 기업에 가상 투자가 가능합니다

<br>

✅ **나의 기업 선택하기 기능**

<table>
  <tr>
    <th style="width: 650px; height: 100px;">데스크탑 & 태블릿 버전</th>
    <th style="width: 350px; height: 100px;">모바일 버전</th>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/23567501-c270-44d2-8e8b-9843efd2afbf" alt="데스크탑 & 태블릿 버전 이미지"></td>
    <td><img src="https://github.com/user-attachments/assets/1483e44d-3e49-4ea4-84e4-7892246ab71f" alt="모바일 버전 이미지"></td>
  </tr>
</table>

<br>

✅ **비교 대상 기업 선택하기 기능**

<table>
  <tr>
    <th style="width: 650px; height: 100px;">데스크탑 & 태블릿 버전</th>
    <th style="width: 350px; height: 100px;">모바일 버전</th>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/27144652-90c6-4b55-9b00-dcbe08b48115" alt="데스크탑 & 태블릿 버전 이미지"></td>
    <td><img src="https://github.com/user-attachments/assets/ea3e7d65-2872-4298-bc9f-d3e345db1eb5" alt="모바일 버전 이미지"></td>
  </tr>
</table>

<br>

✅ **나의 기업과 비교 대상 기업 목록**

<table>
  <tr>
    <th style="width: 650px; height: 100px;">데스크탑 & 태블릿 버전</th>
    <th style="width: 350px; height: 100px;">모바일 버전</th>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/3ede97c5-fb63-4c71-baa5-6829f0629902" alt="데스크탑 & 태블릿 버전 이미지"></td>
    <td><img src="https://github.com/user-attachments/assets/d1b4d82e-63b5-44a3-b207-587ff2d7f015" alt="모바일 버전 이미지"></td>
  </tr>
</table>

<br>

✅ **기업 비교 결과 확인 (나의 기업 vs 비교 대상 선택 기업), 나의 기업 순위 확인 (나의 기업 vs 전체 기업) 결과 불러오기 기능 - 나의 기업은 자동 하이라이트 표시**

<table>
  <tr>
    <th style="width: 650px; height: 100px;">데스크탑 & 태블릿 버전</th>
    <th style="width: 350px; height: 100px;">모바일 버전</th>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/cc6a42b6-0b8c-40e9-b108-5b7bc923a454" alt="데스크탑 & 태블릿 버전 이미지"></td>
    <td><img src="https://github.com/user-attachments/assets/2818b0b8-8a23-466b-84b3-15e2843b5259" alt="모바일 버전 이미지"></td>
  </tr>
</table>

---

<br>

## 5. 팀 프로젝트에서 내가 구현한 API 명세

| **API 이름**         | **엔드포인트**             | **메서드** | **설명**                                                            | **요청 매개변수**                                                                                                                                                                  | **응답 본문(성공 시)**                                                                                                                                        | **에러 응답 예시**                                                                                                                                                                                                                                                                                                       |
| -------------------- | -------------------------- | ---------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 기업 리스트 조회 API | /api/companies             | GET        | 전체 기업 리스트를 조회하는 API. 페이지네이션, 검색, 정렬 기능 제공 | page (정수, 선택)<br>limit (정수, 선택)<br>search (문자열, 선택)<br>sort_by (문자열, 선택)<br>order (문자열, 선택)                                                       | 페이지 번호, 한 페이지당 기업 수, 총 기업 수, 기업 정보 목록 포함<br>기업 정보: id, name, logoUrl, description, category, totalInvestment, revenue, employees | {"error": "기업 리스트를 가져오는 중 오류가 발생했습니다."}                                                                                                                                                                                                                                                            |

---

<br>

## 6. 프로젝트 구조

### Frontend

```
📦vms_fe
 ┣ 📂public
 ┃ ┣ 📂images
 ┃ ┃ ┗ 📜company_logo.png
 ┃ ┣ 📜favicon.png
 ┃ ┗ 📜index.html
 ┣ 📂src
 ┃ ┣ 📂API
 ┃ ┃ ┣ 📜CompanyInvestDetailAPI.js
 ┃ ┃ ┣ 📜DefaultPageAPI.js
 ┃ ┃ ┗ 📜api.js
 ┃ ┣ 📂assets
 ┃ ┃ ┗ 📂images
 ┃ ┃ ┃ ┣ 📜ic_check.svg
 ┃ ┃ ┃ ┣ 📜ic_circle.svg
 ┃ ┃ ┃ ┣ 📜ic_delete.svg
 ┃ ┃ ┃ ┣ 📜ic_delete_circle_small.svg
 ┃ ┃ ┃ ┣ 📜ic_kebab.svg
 ┃ ┃ ┃ ┣ 📜ic_minus.svg
 ┃ ┃ ┃ ┣ 📜ic_password_eye_close.svg
 ┃ ┃ ┃ ┣ 📜ic_password_eye_open.svg
 ┃ ┃ ┃ ┣ 📜ic_plus.svg
 ┃ ┃ ┃ ┣ 📜ic_restart.svg
 ┃ ┃ ┃ ┣ 📜ic_search.svg
 ┃ ┃ ┃ ┣ 📜ic_toggle.svg
 ┃ ┃ ┃ ┣ 📜logo_desktop_tablet.svg
 ┃ ┃ ┃ ┗ 📜logo_mobile.svg
 ┃ ┣ 📂components
 ┃ ┃ ┣ 📂common
 ┃ ┃ ┃ ┣ 📜AddCompanyBtn.js
 ┃ ┃ ┃ ┣ 📜AddCompanyBtn.module.css
 ┃ ┃ ┃ ┣ 📜CompanyCard.js
 ┃ ┃ ┃ ┣ 📜CompanyCard.module.css
 ┃ ┃ ┃ ┣ 📜CompanyDataPerRow.js
 ┃ ┃ ┃ ┣ 📜CompanyDataPerRow.module.css
 ┃ ┃ ┃ ┣ 📜CompanyDataPerRowNoRank.js
 ┃ ┃ ┃ ┣ 📜CompanyDataPerRowNoRank.module.css
 ┃ ┃ ┃ ┣ 📜CompareCompanyBtn.js
 ┃ ┃ ┃ ┣ 📜CompareCompanyBtn.module.css
 ┃ ┃ ┃ ┣ 📜CompareOtherCompanyBtn.js
 ┃ ┃ ┃ ┣ 📜CompareOtherCompanyBtn.module.css
 ┃ ┃ ┃ ┣ 📜Dropdown.js
 ┃ ┃ ┃ ┣ 📜Dropdown.module.css
 ┃ ┃ ┃ ┣ 📜DropdownForEdit.js
 ┃ ┃ ┃ ┣ 📜DropdownForEdit.module.css
 ┃ ┃ ┃ ┣ 📜DropdownMiddleSize.js
 ┃ ┃ ┃ ┣ 📜DropdownMiddleSize.module.css
 ┃ ┃ ┃ ┣ 📜DropdownSmallSize.js
 ┃ ┃ ┃ ┣ 📜DropdownSmallSize.module.css
 ┃ ┃ ┃ ┣ 📜HeaderColumns.js
 ┃ ┃ ┃ ┣ 📜HeaderColumns.module.css
 ┃ ┃ ┃ ┣ 📜InputBar.js
 ┃ ┃ ┃ ┣ 📜InputBar.module.css
 ┃ ┃ ┃ ┣ 📜InvestmentComment.js
 ┃ ┃ ┃ ┣ 📜InvestmentComment.module.css
 ┃ ┃ ┃ ┣ 📜LargeBtn.js
 ┃ ┃ ┃ ┣ 📜LargeBtn.module.css
 ┃ ┃ ┃ ┣ 📜MediumBtn.js
 ┃ ┃ ┃ ┣ 📜MediumBtn.module.css
 ┃ ┃ ┃ ┣ 📜OutlineBtn.js
 ┃ ┃ ┃ ┣ 📜OutlineBtn.module.css
 ┃ ┃ ┃ ┣ 📜Pagination.js
 ┃ ┃ ┃ ┣ 📜Pagination.module.css
 ┃ ┃ ┃ ┣ 📜ResetBtn.js
 ┃ ┃ ┃ ┣ 📜ResetBtn.module.css
 ┃ ┃ ┃ ┣ 📜SearchBar.js
 ┃ ┃ ┃ ┣ 📜SearchBar.module.css
 ┃ ┃ ┃ ┣ 📜SearchBarSmall.js
 ┃ ┃ ┃ ┣ 📜SearchBarSmall.module.css
 ┃ ┃ ┃ ┣ 📜SelectBtn.js
 ┃ ┃ ┃ ┗ 📜SelectBtn.module.css
 ┃ ┃ ┣ 📜DataRowSetRender.js
 ┃ ┃ ┣ 📜DataRowSetRender.module.css
 ┃ ┃ ┣ 📜DataRowSetRenderNoRank.js
 ┃ ┃ ┣ 📜DataRowSetRenderNoRank.module.css
 ┃ ┃ ┣ 📜MessagePopUpOneBtn.js
 ┃ ┃ ┣ 📜MessagePopUpOneBtn.module.css
 ┃ ┃ ┣ 📜MessagePopUpTwoBtn.js
 ┃ ┃ ┣ 📜MessagePopUpTwoBtn.module.css
 ┃ ┃ ┣ 📜ModalInvestment.js
 ┃ ┃ ┣ 📜ModalInvestment.module.css
 ┃ ┃ ┣ 📜ModalInvestmentUpdate.js
 ┃ ┃ ┣ 📜ModalInvestmentUpdate.module.css
 ┃ ┃ ┣ 📜ModalPassword.js
 ┃ ┃ ┣ 📜ModalPassword.module.css
 ┃ ┃ ┣ 📜ModalSelectComparision.js
 ┃ ┃ ┣ 📜ModalSelectComparision.module.css
 ┃ ┃ ┣ 📜ModalSelectMyEnterprise.js
 ┃ ┃ ┣ 📜ModalSelectMyEnterprise.module.css
 ┃ ┃ ┣ 📜PageNav.js
 ┃ ┃ ┣ 📜PageNav.module.css
 ┃ ┃ ┣ 📜companyInfoList.js
 ┃ ┃ ┣ 📜companyItem.js
 ┃ ┃ ┗ 📜companyItem.module.css
 ┃ ┣ 📂context
 ┃ ┃ ┣ 📜CompanyDataContext.js
 ┃ ┃ ┣ 📜DropdownContext.js
 ┃ ┃ ┗ 📜ModalContext.js
 ┃ ┣ 📂hook
 ┃ ┃ ┣ 📜useGetCompanyData.js
 ┃ ┃ ┗ 📜usePageHandler.js
 ┃ ┣ 📂pages
 ┃ ┃ ┣ 📜CompanyInvestDetail.js
 ┃ ┃ ┣ 📜CompanyInvestDetail.module.css
 ┃ ┃ ┣ 📜CurrentStateCompare.js
 ┃ ┃ ┣ 📜CurrentStateCompare.module.css
 ┃ ┃ ┣ 📜CurrentStateInvest.js
 ┃ ┃ ┣ 📜CurrentStateInvest.module.css
 ┃ ┃ ┣ 📜DefaultPage.js
 ┃ ┃ ┣ 📜DefaultPage.module.css
 ┃ ┃ ┣ 📜MyCompanyCompare.js
 ┃ ┃ ┗ 📜MyCompanyCompare.module.css
 ┃ ┣ 📂styles
 ┃ ┃ ┗ 📜reset.css
 ┃ ┣ 📂utils
 ┃ ┃ ┣ 📜convertTo100mil.js
 ┃ ┃ ┣ 📜similarity.js
 ┃ ┃ ┗ 📜sorting.js
 ┃ ┣ 📜App.css
 ┃ ┣ 📜App.js
 ┃ ┣ 📜index.css
 ┃ ┗ 📜index.js
 ┣ 📜.env
 ┣ 📜jsconfig.json
 ┣ 📜package-lock.json
 ┗ 📜package.json
```

### Backend

```
📦vms_be
 ┣ 📂prisma
 ┃ ┣ 📂migrations
 ┃ ┃ ┣ 📂20240819094145_init
 ┃ ┃ ┃ ┗ 📜migration.sql
 ┃ ┃ ┣ 📂20240820003106_add
 ┃ ┃ ┃ ┗ 📜migration.sql
 ┃ ┃ ┣ 📂20240826093414_add_new_selection_count
 ┃ ┃ ┃ ┗ 📜migration.sql
 ┃ ┃ ┣ 📂20240826101216_add_new_field_vms_investment
 ┃ ┃ ┃ ┗ 📜migration.sql
 ┃ ┃ ┣ 📂20240826101732_add_delete_model_selection
 ┃ ┃ ┃ ┗ 📜migration.sql
 ┃ ┃ ┗ 📂20240826124937_add_virtual_investment_type_modify
 ┃ ┃ ┃ ┗ 📜migration.sql
 ┃ ┗ 📜schema.prisma
 ┣ 📂seeders
 ┃ ┣ 📜CompanyData.js
 ┃ ┣ 📜investmentData.js
 ┃ ┗ 📜seed.js
 ┣ 📂src
 ┃ ┣ 📂errors
 ┃ ┃ ┣ 📜CommonException.js
 ┃ ┃ ┗ 📜CustomExceptions.js
 ┃ ┣ 📂middlewares
 ┃ ┃ ┣ 📜asyncHandler.js
 ┃ ┃ ┗ 📜errorHandler.js
 ┃ ┗ 📂routes
 ┃ ┃ ┣ 📜companyRoutes.js
 ┃ ┃ ┗ 📜investmentRoutes.js
 ┣ 📂utils
 ┃ ┣ 📜initializeVirtualInvestment.js
 ┃ ┗ 📜resetIdSequence.js
 ┣ 📜.env
 ┣ 📜api_test.http
 ┣ 📜package-lock.json
 ┣ 📜package.json
 ┗ 📜server.js
```

---

## 7. 학습 내용

## 이번 프로젝트를 통해 배운 점은 다음과 같습니다:

## Frontend
### React를 활용한 기업 비교 페이지 구현
1. 컴포넌트 상태 관리 ( `useState` ) <br>
- 여러 개의 상태 변수를 `useState` 로 관리하여 UI 상태를 유동적으로 변경하는 방법을 배웠습니다.<br>
- 특히 모달 창 열기 / 닫기, 선택된 기업 목록, 추가된 기업 목록, 로딩 상태 등 다양한 상태 변수를 독립적으로 관리하여 복잡한 UI 동작을 처리하는 법을 익혔습니다.<br>
- 이 과정에서 `useState` 를 활용한 상태 관리를 통해 UI 요소를 제어하고 사용자 입력에 즉각 반응하는 기능을 구현할 수 있었습니다.

2. `useEffect` 를 통한 사이드 이펙트 관리 <br>
- API 호출, 데이터 정렬, UI 렌더링 등을 `useEffect` 훅을 활용하여 처리하는 방법을 배웠습니다.<br>
- 컴포넌트가 처음 렌더링될 때 서버로부터 데이터를 불러오는 것부터, 상태가 변경될 때마다 새로운 데이터를 기반으로 정렬된 결과를 렌더링하는 작업까지 사이드 이펙트를 관리하는 중요한 개념을 익혔습니다.<br>
- 이러한 사이드 이펙트는 React의 `useEffect` 를 통해 깔끔하게 관리할 수 있었습니다.

```jsx
useEffect(() => {
  const getCompanies = async () => {
    setIsLoading(true);
    try {
      const data = await fetchCompanies();
      setAllCompanies(data);
    } catch (error) {
      console.error("기업 데이터를 가져오는 데 실패했습니다.");
    } finally {
      setIsLoading(false);
    }
  };
  getCompanies();
}, []);
```

3. 상태 기반으로 로딩 상태 관리 <br>
- `isLoading` 상태를 사용해 데이터를 불러오거나 정렬할 때 로딩 상태를 표시하는 방법을 구현했습니다.<br>
- 이를 통해 비동기 작업 중 사용자에게 로딩 중임을 알리는 UX 개선을 실현할 수 있었습니다.<br>
- API 호출이 완료되면 로딩 상태를 해제하고 데이터를 화면에 반영하여 사용자가 처리 상태를 명확히 인식할 수 있도록 했습니다.

4. 동적 데이터 정렬 및 비교 로직 구현 <br>
- 선택된 기업과 추가된 기업을 정렬하는 기능을 구현하면서, 사용자가 선택한 정렬 옵션에 따라 데이터를 동적으로 정렬하여 결과를 렌더링하는 로직을 배웠습니다.<br>
- 특히, `sortCompanies` 함수를 통해 데이터를 매출액, 고용 인원 등 다양한 기준으로 정렬하고, 이를 실시간으로 반영하는 기능을 구현했습니다.


```jsx
const sortedData = sortCompanies(combinedCompanies, option);
setSortedCompaniesForComparison(sortedData);
```

5. 비교 결과와 순위 데이터를 동적으로 처리 <br>
- 사용자가 선택한 기업을 기준으로 다른 기업들과 비교하고, 나의 기업의 순위를 동적으로 불러오는 로직을 `useCallback` 과 `useEffect`를 통해 효율적으로 처리하는 방법을 배웠습니다. <br>
- 특히, `fetchRankedCompanies` 함수를 사용해 기업들의 순위를 동적으로 불러오고 이를 실시간으로 UI에 반영하는 과정을 통해 비동기 데이터 처리의 중요성을 깨달았습니다.

6. 라우팅을 통한 페이지 네비게이션 ( `useNavigate` ) <br>
- `useNavigate` 를 사용하여 선택한 기업의 상세 페이지로 동적으로 이동할 수 있는 네비게이션 기능을 구현했습니다. <br>
- 사용자가 특정 기업에 투자하기 위해 버튼을 클릭하면 해당 기업의 ID를 기반으로 URL을 변경하여 적절한 페이지로 이동하는 방법을 배웠습니다.

```jsx
const handleInvestmentClick = () => {
  if (selectedCompanies.length > 0) {
    const companyId = selectedCompanies[0].id;
    navigate(`/id/${companyId}`);
  }
};
```

7. 컴포넌트의 재사용성 향상 <br>
- `CompanyCard`, `DropdownSmallSize`, `ModalSelectComparision`와 같은 공통 컴포넌트를 활용하여, 다양한 상황에서도 재사용할 수 있는 모듈화된 컴포넌트를 만들 수 있었습니다.<br>
- 이러한 재사용 가능한 컴포넌트들은 유지보수성을 높이고 코드 중복을 줄이는 데 큰 도움이 되었습니다.

<br>

=> **이와 같은 경험을 통해 React 상태 관리, 비동기 데이터 처리, 동적 정렬 및 비교 로직 구현, 그리고 사용자 경험을 개선하는 방법을 심도 있게 학습할 수 있었습니다.**

<br>

## Backend
### 기업 데이터 처리 및 정렬 API 구현
1. Axios를 통한 API 통신 <br>
- `axios`를 사용하여 서버와의 통신을 비동기로 처리하는 방법을 배웠습니다.<br> 
- 특히, 서버에서 제공하는 기업 데이터를 가져오기 위해 `GET` 요청을 보내고, 이를 비동기적으로 처리하여 페이지네이션 기능을 구현할 수 있었습니다. <br>
- 요청 시 `params`를 활용하여 쿼리 매개변수를 쉽게 전달하는 방법도 익혔습니다.

```jsx
const response = await axios.get("https://view-my-startup.onrender.com/api/companies", {
  params: { page, limit },
});
```

2. 데이터 정렬 로직 구현 <br>
- 서버에서 가져온 기업 데이터를 사용자가 원하는 기준(누적 투자금액, 매출액, 고용 인원)에 따라 정렬하는 `sortCompanies` 함수를 구현하면서, 다양한 정렬 옵션을 처리하는 방법을 배웠습니다.<br>
- 정렬된 결과를 효율적으로 관리하기 위해 `switch` 문을 활용한 방식으로 코드의 가독성을 높이는 방법을 익혔습니다.

```jsx
const sortedList = [...companies];
sortedList.sort((a, b) => b.totalInvestment - a.totalInvestment); // 누적 투자금액 높은순
```

3. 상태를 기반으로 유동적인 순위 계산 <br>
- `getCompaniesForRanking` 함수를 통해, 나의 기업을 기준으로 근접한 기업들의 순위를 계산하는 로직을 작성했습니다.<br>
- 특히, 사용자의 기업이 리스트 중 어느 위치에 있느냐에 따라, 위 또는 아래에 위치한 기업들을 동적으로 불러오고 정렬하는 방법을 구현하는 과정에서 순위 계산 로직을 심도 있게 이해할 수 있었습니다.<br>
- 예를 들어, 나의 기업이 중간에 위치할 경우 상위 2개와 하위 2개의 기업을 조회하는 방식 등을 처리하는 방법을 배웠습니다.

```jsx
if (myCompanyIndex > 1 && myCompanyIndex < sortedCompanies.length - 2) {
  const topCompanies = sortedCompanies.slice(myCompanyIndex - 2, myCompanyIndex);
  const bottomCompanies = sortedCompanies.slice(myCompanyIndex + 1, myCompanyIndex + 3);
  return [...topCompanies, sortedCompanies[myCompanyIndex], ...bottomCompanies];
}
```

4. 에러 처리 및 디버깅 경험 <br>
- 서버에서 잘못된 데이터를 받을 경우나, 유효하지 않은 기업 ID가 제공되었을 때 적절한 에러 처리를 통해 디버깅을 쉽게 할 수 있도록 하였습니다.<br>
- 이를 통해 API 호출 중 발생할 수 있는 다양한 오류를 다루고, 사용자가 잘못된 데이터를 받을 경우 사용자에게 알림을 주는 방식으로 에러 처리 로직을 강화할 수 있었습니다.

```jsx
if (!Array.isArray(allCompanies)) {
  throw new Error("서버에서 잘못된 데이터 형식이 반환되었습니다.");
}
```

5. 코드의 재사용성 및 유지보수성 강화 <br>
- `fetchCompanies`, `sortCompanies`, `getCompaniesForRanking` 함수들은 모두 다양한 상황에서 재사용 가능하게 작성했습니다.<br>
- 이러한 함수의 모듈화를 통해, 코드의 유지보수성을 높이고 다른 기능에서 쉽게 재사용할 수 있도록 한 점에서 큰 학습을 얻었습니다.

<br>

=> **이와 같은 경험을 통해 API 호출, 데이터 처리, 정렬 로직, 에러 처리 등과 같은 백엔드 통신 및 데이터 핸들링 기술을 심도 있게 학습할 수 있었습니다.**

