<template>
  <section id="about" class="section section__container">
    <h1>About me</h1>
    <p>
      주로 Vue작업을 하는 프론트엔드 개발자입니다. 프로젝트 구축은 2건을
      해보았고 신세계 스타필드 모바일 웹/앱 유지 및 보수 업무를 하고 있습니다.
    </p>
    <div class="about__majors">
      <div class="major">
        <div class="major__icon">
          <i class="fab fa-html5"></i>
        </div>
        <div class="major__title">Front-end</div>
        <div class="major__description">HTML, CSS, JavaScript, Vue</div>
      </div>
      <div class="major">
        <div class="major__icon">
          <i class="fab fa-html5"></i>
        </div>
        <div class="major__title">Front-end</div>
        <div class="major__description">HTML, CSS, JavaScript, Vue</div>
      </div>
      <div class="major">
        <div class="major__icon">
          <i class="fab fa-html5"></i>
        </div>
        <div class="major__title">Front-end</div>
        <div class="major__description">HTML, CSS, JavaScript, Vue</div>
      </div>
    </div>
    <div class="about__jobs">
      <div class="job">
        <img
          src="@/assets/imgs/company/soulware.png"
          alt="soulware"
          class="job__logo"
        />
        <div class="job__description">
          <p class="job__name">소울웨어</p>
          <p class="job__period">2019.07 ~ 2020.01</p>
        </div>
      </div>
      <div class="job">
        <img
          src="@/assets/imgs/company/darum.png"
          alt="soulware"
          class="job__logo"
        />
        <div class="job__description">
          <p class="job__name">다름</p>
          <p class="job__period">2020.04 ~ 재직중</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style></style>
