<template>
  <section id="skills" class="section">
    <div class="section__container">
      <h1>Skills</h1>
      <h2>Skills & Attributes</h2>
      <p>
        개발자는 새로운 것을 익히고, 학습하는 것을 멈추면 안된다고 생각해와서
        업무가 없을 때는 꾸준히 공부에 매진하고 있습니다. vue 뿐만 아니라 react,
        node.js express에도 관심이 있어서 배우고 있습니다. 또한 지금은
        퍼블리셔가 많이 도와주지만 css도 꾸준히 익히고 있습니다.<br />
        REST환경으로 구성된 서버에서 json값들을 받아와서 적절하게 보여줄 수 있는
        vue작업이 정말 재미있습니다.
      </p>
      <div class="skillset">
        <div class="skillset__left">
          <h3 class="skillset__title">Skills</h3>
          <div class="skill" v-for="(skill, idx) in skills" :key="idx">
            <div class="skill__description">
              <span>{{ skill.name }}</span>
              <span>{{ skill.percent }}</span>
            </div>
            <div class="skill__bar">
              <div
                class="skill__value"
                :style="`width: ${skill.percent}`"
              ></div>
            </div>
          </div>
        </div>
        <div class="skillset__right">
          <div class="tools">
            <h3 class="skillset__title">Tools</h3>
            <ul class="tools__list">
              <li v-for="(tool, idx) in tools" :key="idx">
                <span>{{ tool }}</span>
              </li>
            </ul>
          </div>
          <div class="etc">
            <h3 class="skillset__title">Etc</h3>
            <ul class="etc__list">
              <li v-for="(etc, idx) in etcList" :key="idx">
                <span>{{ etc }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        { name: "HTML", percent: "99%" },
        { name: "JavaScript", percent: "75%" },
        { name: "Vue", percent: "80%" }
      ],
      tools: ["Visual Studio Code", "IntelliJ", "Sqlyog"],
      etcList: ["Git", "Pull-Up"]
    };
  }
};
</script>

<style></style>
