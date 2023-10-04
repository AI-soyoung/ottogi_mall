# ⚡️ 오뚜기몰 활성화를 위한 캐치프레이즈 생성 서비스
- 2023 aws X streamlit X 오뚜기 해커톤 1등 수상작

<br>

## 🍚 팀 뚜기두밥
<table align="center">
  <tr height="155px">
    <td align="center" width="160px" height="155px">
      <a href="https://github.com/seohii66"><img src="https://avatars.githubusercontent.com/u/86870736?v=4"/></a>
    </td>
    <td align="center" width="160px" height="155px">
      <a href="https://github.com/Jaehyeonee"><img src="https://avatars.githubusercontent.com/u/92504386?v=4"/></a>
    </td>
    <td align="center" width="160px" height="155px">
      <a href="https://github.com/AI-soyoung"><img src="https://avatars.githubusercontent.com/u/126646180?v=4"/></a>
    </td>
    <td align="center" width="160px" height="155px">
      <a href="https://github.com/euvely"><img src="https://avatars.githubusercontent.com/u/102321531?v=4"/></a>
    </td>
    <td align="center" width="160px" height="155px">
      <a href="https://github.com/yyyeun"><img src="https://avatars.githubusercontent.com/u/38968449?v=4"/></a>
    </td>
  </tr>
  <tr height="80px">
    <td align="center" width="160px">
      <a href="https://github.com/seohii66">김서희</a>
    </td>
    <td align="center" width="160px">
      <a href="https://github.com/Jaehyeonee">안재현</a>
    </td>
    <td align="center" width="160px">
      <a href="https://github.com/AI-soyoung">임소영</a>
    </td>
    <td align="center" width="160px">
      <a href="https://github.com/euvely">최유진</a>
    </td>
    <td align="center" width="160px">
      <a href="https://github.com/yyyeun">허예은</a>
    </td>
  </tr>
</table>
&nbsp;
<br><br>

## 💡 아이디어 소개
오뚜기는 좋은 아이템을 가지고 있지만, 자사몰 이용률이 낮기에 이유를 분석하여, 
이용률을 높이고 성장효과를 극대화하기 위한 방안을 제안

1. 리뷰 및 재고 데이터 분석
2. 관리자용 모니터링 시스템
3. 생성 AI를 활용한 홍보 캐치프레이즈를 제작

<br>

## 🖼️ 아키텍쳐
<div align="center">
  <img src='https://github.com/AI-soyoung/ottogi_mall/blob/a8d9285fd4f4072abb7cba0cfa8bc4a32cd71d67/%E1%84%84%E1%85%AE%E1%84%80%E1%85%B5%E1%84%83%E1%85%AE%E1%84%87%E1%85%A1%E1%86%B8%20%E1%84%8B%E1%85%A1%E1%84%8F%E1%85%B5%E1%84%90%E1%85%A6%E1%86%A8%E1%84%8E%E1%85%A7.png'>
</div>

1. `오뚜기 자사몰`에 유저들이 리뷰를 작성합니다.
2. `aws lambda`를 통해 리뷰 데이터를 매일 크롤링하고, `aws rds`에 저장합니다.
3. 저장된 데이터를 기반으로 `Google Colab`에서 데이터를 분석한 뒤, 결과를 `aws rds`에 다시 저장합니다.
4. 정제되고 분석된 데이터는 `aws cloud9` 상에서 구현된 `streamlit`으로 넘어갑니다.
5. 마케팅 담당자가 자주 발생하는 네거티브 리뷰에 대한 해결방안을 고안할 수 있도록, `slack`을 통해 알림과 내용을 전달합니다.
6. 마케팅 담당자는 연구개발팀에 개선 방안 고안과 연구를 요청합니다.
7. 마케팅 담당자가 연구개발팀으로부터 개선 방안을 전달받으면, 담당자는 이를 `streamlit` 에 입력하고, `ChatGPT`에 개선점을 기반으로한 홍보 문구 작성을 요청하는 프롬프트를 자동으로 보냅니다.
8. `ChatGPT`는 캐치프레이즈를 생성한 뒤 관리자의 컨펌을 받은 홍보물에 한하여, 오뚜기 자사몰 배너를 `자동으로 업데이트`하고, `aws sns`를 통해 해당 네거티브 리뷰 데이터를 작성한 사용자에게 자동으로 피드백 연락이 가게 합니다.
<br>
