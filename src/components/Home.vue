<!-- @format -->

<template>
  <nav class="navbar navbar-expand-md navbar-dark bg-primary mb-2 sticky-top">
    <div class="container-fluid">
      <a class="navbar-brand" href="/"
        ><img src="/img/logo.svg" width="80" height="30" /><small
          class="badge rounded-pill bg-secondary"
          >Beta</small
        ></a
      ><button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link" aria-current="page" href="/courses/async"
              >課程</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="/arrange">模擬排課</a>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              href="//forms.gle/9zNafkf9hC5AWB7v6"
              target="_blank"
              >意見回饋 <i class="fas fa-external-link-alt"></i
            ></a>
          </li>
        </ul>
        <ul class="navbar-nav flex-wrap ms-md-auto">
          <li class="nav-item">
            <a class="nav-link" href="/auth/login">登入</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="container bg-light p-2 my-2 sticky-top" id="searchBar">
    <div class="row justify-content-center">
      <div class="col-12 col-sm-8 col-md-6">
        <form action="/courses/async" method="get">
          <div class="input-group">
            <input
              class="form-control"
              id="search"
              type="text"
              name="search"
              value=""
              placeholder="任課教師/科目名稱/課程代碼"
            /><input
              class="text-light btn btn-primary"
              type="submit"
              value="送出查詢"
            />
          </div>
        </form>
      </div>
    </div>
  </div>

  <div class="container">
    <div class="row">
      <div v-for="(item, index) in courses_data" :key="index" class="col-sm-12 col-md-4 col-lg-3 mb-3">
        <div class="card focus h-100">
          <div class="card-body">
            <a href="#" class="stretched-link"></a>
            <h6 class="fw-bold card-subtitle mb-2 text-muted">{{item['學校']['校區'][0]}}</h6>
            <div class="fw-bold h5 card-title">{{item['科目']['name']}}</div>
            <h6 class="fw-bold card-subtitle mb-2">
              {{item['任課教師']['正課'][0]}}
              <div class="float-end"><span class="badge rounded-start bg-primary">{{item['上課日期_節次'][0]['d']}}</span><span class="badge rounded-end bg-secondary">{{item['上課日期_節次'][0]['t']}}</span></div>
            </h6>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      courses_data: [
        {
          上課日期_節次: [{ d: "1", t: "0304" }],
          _id: "6107cf89868b060fdafbc10a",
          制別: "大學部",
          科目: { id: "00756", name: "公民與多元社會" },
          開班_選課人數: "60／60",
          任課教師: { 正課: ["董倫銓"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0304" }],
          _id: "6107cf89868b060fdafbc10b",
          制別: "大學部",
          科目: { id: "02067", name: "環境保護概論" },
          開班_選課人數: "80／50",
          任課教師: { 正課: ["簡名瑀"], 實習: [] },
          年級: "0",
          學校: { 教室: ["E202"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0506" }],
          _id: "6107cf89868b060fdafbc10c",
          制別: "大學部",
          科目: { id: "02069", name: "音樂與生活" },
          開班_選課人數: "60／60",
          任課教師: { 正課: ["劉馥綾"], 實習: [] },
          年級: "0",
          學校: { 教室: ["H101"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "遠距教學",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0506" }],
          _id: "6107cf89868b060fdafbc10d",
          制別: "大學部",
          科目: { id: "00752", name: "華人歷史與文化" },
          開班_選課人數: "60／60",
          任課教師: { 正課: ["陳祥雲"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B406"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0506" }],
          _id: "6107cf89868b060fdafbc10e",
          制別: "大學部",
          科目: { id: "00751", name: "世界文明" },
          開班_選課人數: "70／70",
          任課教師: { 正課: ["康才媛"], 實習: [] },
          年級: "0",
          學校: { 教室: ["E202"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0506" }],
          _id: "6107cf89868b060fdafbc10f",
          制別: "大學部",
          科目: { id: "00803", name: "台灣開發與轉型" },
          開班_選課人數: "55／53",
          任課教師: { 正課: ["吳雅琪"], 實習: [] },
          年級: "0",
          學校: { 教室: ["D102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0506" }],
          _id: "6107cf89868b060fdafbc110",
          制別: "大學部",
          科目: { id: "00754", name: "民主與法治" },
          開班_選課人數: "60／60",
          任課教師: { 正課: ["宋筱元"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B103"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0708" }],
          _id: "6107cf89868b060fdafbc111",
          制別: "大學部",
          科目: { id: "00754", name: "民主與法治" },
          開班_選課人數: "60／60",
          任課教師: { 正課: ["宋筱元"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B103"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0708" }],
          _id: "6107cf89868b060fdafbc112",
          制別: "大學部",
          科目: { id: "00748", name: "性別與影像" },
          開班_選課人數: "60／18",
          任課教師: { 正課: ["沈慶珩"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0708" }],
          _id: "6107cf89868b060fdafbc113",
          制別: "大學部",
          科目: { id: "00751", name: "世界文明" },
          開班_選課人數: "70／70",
          任課教師: { 正課: ["康才媛"], 實習: [] },
          年級: "0",
          學校: { 教室: ["E202"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0708" }],
          _id: "6107cf89868b060fdafbc114",
          制別: "大學部",
          科目: { id: "02035", name: "音樂欣賞" },
          開班_選課人數: "60／59",
          任課教師: { 正課: ["劉馥綾"], 實習: [] },
          年級: "0",
          學校: { 教室: ["H101"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "遠距教學",
          畢業班: "N",
          學期數: "上學期",
          說明: "遠距(限60人)",
        },
        {
          上課日期_節次: [{ d: "1", t: "0708" }],
          _id: "6107cf89868b060fdafbc115",
          制別: "大學部",
          科目: { id: "00751", name: "世界文明" },
          開班_選課人數: "60／23",
          任課教師: { 正課: ["陳祥雲"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B406"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0304" }],
          _id: "6107cf89868b060fdafbc109",
          制別: "大學部",
          科目: { id: "00805", name: "西方藝術與美感" },
          開班_選課人數: "55／55",
          任課教師: { 正課: ["許美玲"], 實習: [] },
          年級: "0",
          學校: { 教室: ["D102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0940" }],
          _id: "6107cf89868b060fdafbc117",
          制別: "大學部",
          科目: { id: "00748", name: "性別與影像" },
          開班_選課人數: "60／14",
          任課教師: { 正課: ["沈慶珩"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "2", t: "0102" }],
          _id: "6107cf89868b060fdafbc118",
          制別: "大學部",
          科目: { id: "02058", name: "生命科學" },
          開班_選課人數: "60／47",
          任課教師: { 正課: ["許綸中"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
        {
          上課日期_節次: [{ d: "1", t: "0102" }],
          _id: "6107cf89868b060fdafbc107",
          制別: "大學部",
          科目: { id: "00755", name: "國家與市場" },
          開班_選課人數: "60／60",
          任課教師: { 正課: ["董倫銓"], 實習: [] },
          年級: "0",
          學校: { 教室: ["B102"], 校區: ["台北"] },
          選別: "通識",
          學分: "2",
          類別: "",
          畢業班: "N",
          學期數: "上學期",
          說明: "",
        },
      ],
    };
  },
  mounted() {
    let headers = new Headers();
    headers.append("Content-Type", "application/json");
    headers.append("Accept", "application/json");
    headers.append("Origin", "http://localhost:8080");

    fetch("https://up.mcuosc.dev/courses/json", { headers: headers })
      .then(function (response) {
        return response.json();
      })
      .then(function (data) {
        console.log(data);
      });
  },
};
</script>

<style scoped>
body {
  font-family: "Noto Sans TC", var(--bs-font-sans-serif);
}

.focus:hover,
.focus:focus {
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15) !important;
}

.focus {
  transition: box-shadow 0.3s ease-in-out;
}

.card > .card-body > h6 > div > span.badge {
  border-radius: 0%;
}

#searchBar {
  z-index: 1010;
  top: 60px;
  transition: top 0.3s;
}
</style>
