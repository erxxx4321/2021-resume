<template>
	<div class="container">
		<header>
			<div class="square">
				<h2>YF</h2>
			</div>
			<h1 v-if="lang == 'EN'">Chin Yu Fang (Kaori)</h1>
			<h1 v-else-if="lang == 'CN'">秦譽芳 (Kaori)</h1>
			<select v-model="lang" id="languageSwitcher">
				<option v-for="(item, key) in options" :value="item.value" :key="key">{{ item.text }}</option>
			</select>
		</header>
		<div class="content">
			<div class="content-left">
				<div id="biography">
					<h3 class="title">Biography</h3>
					<div class="info" v-if="lang == 'CN'">{{ bioContent.CN.text }}</div>
					<div class="info" v-else-if="lang == 'EN'">{{ bioContent.EN.text }}</div>
				</div>
				<hr />
				<div id="experience">
					<h3 class="title">Experience</h3>
					<div class="info" v-if="lang == 'CN'">
						<div v-for="(item, key) in expContent.CN" :key="key">
							<h4>{{ item.jobTitle }}</h4>
							<p>{{ item.company }}</p>
							<p>{{ item.period }}</p>
							<ul style="padding: 1rem 1.5rem;">
								<li v-for="(des, key) in item.description" :key="key" style="margin-bottom: 0.5rem">{{ des }}</li>
							</ul>
						</div>
					</div>
					<div class="info" v-else-if="lang == 'EN'">
						<div v-for="(item, key) in expContent.EN" :key="key">
							<h4>{{ item.jobTitle }}</h4>
							<p>{{ item.company }}</p>
							<p>{{ item.period }}</p>
							<ul style="padding: 1rem 1.5rem;">
								<li v-for="(des, key) in item.description" :key="key" style="margin-bottom: 0.5rem">{{ des }}</li>
							</ul>
						</div>
					</div>
				</div>
			</div>
			<div class="content-right">
				<div id="skills">
					<h3 class="title">Skills</h3>
					<div style="padding: 0 1.5rem;">
						<ul class="info" v-if="lang == 'CN'">
							<li v-for="(item, key) in skiContent.CN" :key="key" style="margin-bottom: 0.5rem">{{ item }}</li>
						</ul>
						<ul class="info" v-else-if="lang == 'EN'">
							<li v-for="(item, key) in skiContent.EN" :key="key" style="margin-bottom: 0.7rem">{{ item }}</li>
						</ul>
					</div>
				</div>
				<hr />
				<div id="education">
					<h3 class="title">Education</h3>
					<div class="info" v-if="lang == 'CN'">
						<div v-for="(item, key) in eduContent.CN" :key="key" style="margin-bottom: 1.5rem;">
							<h4>{{ item.school }}</h4>
							<p>{{ item.location }}</p>
							<p>{{ item.period }}</p>
							<p style="margin: 0.5rem 0;">{{ item.major }}</p>
						</div>
					</div>
					<div class="info" v-if="lang == 'EN'">
						<div v-for="(item, key) in eduContent.EN" :key="key" style="margin-bottom: 1.5rem;">
							<h4>{{ item.school }}</h4>
							<p>{{ item.location }}</p>
							<p>{{ item.period }}</p>
							<p style="margin: 0.5rem 0;">{{ item.major }}</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<footer>
			<h3 style="margin-bottom: 1.5rem;">Social Links</h3>
			<div>
				<a v-for="(item, key) in contactIcons" :key="key" :href="item.href" class="icons">
					<i :class="item.class" style="font-size: 2.5rem"></i>
				</a>
			</div>
		</footer>
	</div>
</template>

<script>
	export default {
		name: "Resume",
		data() {
			return {
				lang: "EN",
				options: [
					{ value: "CN", text: "Chinese" },
					{ value: "EN", text: "English" },
				],
				bioContent: {
					CN: {
						text:
							"哈囉，我是Kaori，熱衷於程式學習、資訊科技及前端開發，擅長Javascript，近期也在學習VueJS前端框架以及接觸後端、資料庫的基本知識，「保持謙虛，持續學習」是我的信念。",
					},
					EN: {
						text:
							"I am a software development enthusiast and passionate about Frontend development. Currently focusing on learning Vue.js, Vuex. I always stay humble and keep the passion for learning new things.",
					},
				},
				expContent: {
					CN: [
						{
							jobTitle: "行政助理",
							company: "Shinwa, Co., Ltd. ・ 日本福岡",
							period: "03/2019 - 08/2020",
							description: [
								"支援平面印刷作業，處理機器故障問題。",
								"計算部門加工利潤和時間成本，將產能製成可視化圖",
								"開發出使用英數字取代流水號的輸入作業流程。",
								"連線外部表單資料，自動更新月份統計報表。",
							],
						},
						{
							jobTitle: "實習生",
							company: "Treasure Hunt Co., Ltd.・日本福岡",
							period: "09/2018 - 03/2019",
							description: [
								"搜集全日本旅館數據",
								"搜集有關FinTech, IT主題的會議、會展等資訊。",
								"依據旅宿業者需求，為海外部落客打造訪日旅遊行程。",
							],
						},
						{
							jobTitle: "商品攝影師",
							company: "Reusebupo Co., Ltd. ・ 台灣台北",
							period: "03/2017 - 03/2018",
							description: [
								"操作燈光、相機鏡頭及設定，展現產品特色和品質。",
								"錄製商品360度旋轉影片。",
								"使用Photoshop做影像編修。",
								"製作數位攝影教學。",
							],
						},
					],
					EN: [
						{
							jobTitle: "Administrative Assistant",
							company: "Shinwa, Co., Ltd. ・ Fukuoka, Japan",
							period: "03/2019 - 08/2020",
							description: [
								"Supported the printing operation and  fixed common printer error.",
								"Calculated daily processing profit and time cost to increase labour productivity.",
								"Used Excel VBA to automate repetitive tasks and optimize workflow.",
							],
						},
						{
							jobTitle: "Internship",
							company: "Treasure Hunt Co., Ltd.・Fukuoka, Japan",
							period: "09/2018 - 03/2019",
							description: [
								"Collected nationwide hotel data , specified in high-class hotels.",
								"Searched  conferences, events information on FinTech, IT, Business, etc.",
								"Created a travel schedule for oversea bloggers according to client’s request.",
							],
						},
						{
							jobTitle: "Product Photographer",
							company: "Reusebupo Co., Ltd. ・ Taipei, Taiwan",
							period: "03/2017 - 03/2018",
							description: [
								"Manupulated the camera setting,  camera lense, and lighting to display a product features and quality.",
								"Edited images in Photoshop.",
								"Created digital photography tutorials.",
							],
						},
					],
				},
				skiContent: {
					CN: [
						"熟悉Javascript/HTML5/CSS3",
						"前端框架VueJs, Vuex及ReactJs開發經驗",
						"熟悉Git版本控制",
						"熟悉Webpack打包工具及npm插件",
						"具備RESTful API串接經驗",
						"有Microsoft .Net Framework的開發經驗",
						"基礎後端nodeJs, MSSQL資料庫概念",
					],
					EN: [
						"Strong Javascript/HTML5/CSS3 skills.",
						"Extensive experience in JavaScript and other clientside technologies, including modern JavaScript libraries and frameworks(VueJs, ReactJs).",
						"Experienced in working in a GIT based version-control environment.",
						"Familiar with Webpack module bundler and npm plugin.",
						"Experience with web application development using RESTful API",
						"Understanding of and experience with the Microsoft .Net Framework",
						"Basic Backend, Database knowledge.",
					],
				},
				eduContent: {
					CN: [
						{
							school: "國立暨南國際大學",
							location: "台灣",
							period: "09/2012 - 06/2016",
							major: "外國語文學系",
						},
						{
							school: "ASO College Group",
							location: "日本",
							period: "09/2012 - 06/2016",
							major: "日本語學程",
						},
					],
					EN: [
						{
							school: "National Chi Nan University",
							location: "Taiwan",
							period: "09/2012 - 06/2016",
							major: "Foreign Language and Literature",
						},
						{
							school: "ASO College Group",
							location: "Japan",
							period: "09/2012 - 06/2016",
							major: "Japanese course",
						},
					],
				},
				contactIcons: [
					{
						class: "fas fa-link",
						href: "https://kaorichin.netlify.app/",
					},
					{
						class: "fab fa-github icon",
						href: "https://github.com/erxxx4321",
					},
					{
						class: "fab fa-medium-m icon",
						href: "https://medium.com/@erxxx4321",
					},
				],
			};
		},
	};
</script>

<style scoped>
	hr {
		width: 90%;
		color: var(--dark);
	}

	h3 {
		text-transform: uppercase;
	}

	.container {
		width: 900px;
		margin: 0 auto;
		border: 1px solid var(--dark);
		border-top: none;
	}

	header {
		background: var(--primary);
		color: #fff;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 0.7rem;
		position: relative;
	}

	footer {
		background: var(--primary);
		color: #fff;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 1.5rem;
	}

	.icons {
		color: #fff;
		margin: 0 1rem;
	}

	.icons:hover {
		color: var(--dark);
	}

	.square {
		width: 50px;
		height: 50px;
		border: 1px solid #fff;
		text-align: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
		margin-bottom: 10px;
	}

	#languageSwitcher {
		position: absolute;
		bottom: 0;
		right: 0;
		margin: 0.5rem;
		padding: 0.3rem;
		cursor: pointer;
	}

	.content {
		display: flex;
		justify-content: space-evenly;
	}

	.content-left {
		width: 60%;
		padding-left: 1.5rem;
		padding-right: 0.5rem;
	}

	.content-right {
		width: 40%;
		background: var(--secondary);
		padding-left: 1.5rem;
		padding-right: 0.5rem;
	}

	.title {
		padding: 2rem 0 1rem;
	}

	.info {
		padding: 0 0.7rem 1.5rem;
	}
</style>
