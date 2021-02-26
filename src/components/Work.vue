<template>
  <section id="work" class="section">
    <div class="section__container">
      <h1>My work</h1>
      <h2>Projects</h2>
      <div class="work__categories">
        <button
          v-for="(item, idx) in buttons"
          :key="idx"
          class="category__btn"
          :class="{ selected: item.selected }"
          :data-filter="item.filterName"
          @click="btnController"
        >
          {{ item.btnName }}<span class="category__count">{{ item.count }}</span>
        </button>
      </div>
      <div class="work__projects" :class="{ 'anim-out': projectsAnimate }">
        <a
          v-for="(project, idx) in projectList"
          :key="idx"
          href="javascript:;"
          class="project"
          :class="{ invisible: project.classToggle }"
          taget="blank"
          :data-type="project.type"
          ><img class="project__img" :src="project.img" :alt="project.alt" />
          <div class="project__description">
            <h3>{{ project.engTitle }}</h3>
            <span>{{ project.koTitle }}</span>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projectList: [
        {
          type: "*",
          img: "@/assets/imgs/projects/starfield_mobile.png",
          alt: "Starfield_Mobile",
          engTitle: "Starfield Mobile",
          koTitle: "스타필드 모바일 유지보수",
          classToggle: false
        },
        {
          type: "front-end",
          img: "@/assets/imgs/projects/starfield_mobile.png",
          alt: "front-end",
          engTitle: "Front-end",
          koTitle: "프론트엔드",
          classToggle: false
        },
        {
          type: "back-end",
          img: "@/assets/imgs/projects/starfield_mobile.png",
          alt: "back-end",
          engTitle: "Back-end",
          koTitle: "백엔드",
          classToggle: false
        },
        {
          type: "mobile",
          img: "@/assets/imgs/projects/starfield_mobile.png",
          alt: "mobile",
          engTitle: "Mobile",
          koTitle: "모바일",
          classToggle: false
        }
      ],
      projectsAnimate: false
    };
  },
  computed: {
    projectCount() {
      const typeFront = this.projectList.filter(v => {
        return v.type == "front-end";
      });
      const typeBack = this.projectList.filter(v => {
        return v.type == "back-end";
      });
      const typeMobile = this.projectList.filter(v => {
        return v.type == "mobile";
      });
      const count = {
        all: this.projectList.length,
        "front-end": typeFront.length,
        "back-end": typeBack.length,
        mobile: typeMobile.length
      };
      return count;
    },
    buttons() {
      const btns = [
        {
          filterName: "*",
          btnName: "All",
          count: this.projectCount.all,
          selected: true
        },
        {
          filterName: "front-end",
          btnName: "Front-end",
          count: this.projectCount["front-end"],
          selected: false
        },
        {
          filterName: "back-end",
          btnName: "Back-end",
          count: this.projectCount["back-end"],
          selected: false
        },
        {
          filterName: "mobile",
          btnName: "Mobile",
          count: this.projectCount.mobile,
          selected: false
        }
      ];
      return btns;
    }
  },
  methods: {
    btnController(e) {
      const filter =
        e.target.dataset.filter || e.target.parentNode.dataset.filter;
      for (let i = 0, max = this.buttons.length; i < max; i++) {
        if (this.buttons[i].filterName == filter) {
          this.buttons[i].selected = true;
        } else {
          this.buttons[i].selected = false;
        }
      }
      this.projectsAnimate = true;
      this.$forceUpdate();

      setTimeout(() => {
        this.projectList.forEach(project => {
          if (filter == "*" || filter == project.type) {
            project.classToggle = false;
          } else {
            project.classToggle = true;
          }
        });
        this.projectsAnimate = false;
        this.$forceUpdate();
      }, 300);
    }
  },
  mounted() {}
};
</script>

<style></style>
