# JinBang

河南高考数据汇总, 数据来源 [河南省招生办公室网站](http://www.heao.gov.cn/)

**每年的数据都是固定的, 请勿使用本工具反复抓取数据**

data 目录下的数据文件位置及重要结构解释

```
base.json    provinces {省市代号: 省市名称}
			 PC {批次代号: 批次名称}
			 KL {科类代号: 科类名称}
			 schools {省市代号: [院校代号]}

plans.json   {院校代号: {批次代号: {科别代号: {专业代号: {total: 计划录取}}}}}
             所有 total 属性表示该分支之下计划招生合计数
             科别之下的 history 表示上年平行投档线
             叶子对象的 href 属性保存原始页面地址

history.json 上年平行投档线汇总
             planless   本年本科无招生计划的院校 {院校代号: 院校名称}
             renamed    本年名称变化的院校 {院校代号: {old: 原用名, now: 现用名}
             批次代号   {科别代号:[[最低录取分数, 院校代号...]]}
                        是依照本年批次代号, 科别代号整理的最低录取分降序数据,
                        相同最低录取分数的院校收纳到一起

schools.json 院校基本信息, 可用于生成信息表格

fen.json     本年分数段统计, {科别代号: [[分数, 考生人数]...]}
             考生人数为加入政策性照顾分后对应总分及以上考生累计人数

rank.json    综合历史数据和本年计划, 计算出的科类分数段和院校关系
             {科别代号: [[分数, 考生人数, 院校代号]...]}

total.json   分批次, 科类统计生成招生计划
             {total: 计划总数, 批次代号: {total: 批次总数, 科别代号: 科别总数}}
```

# summary

2017 年招生信息概况

```
省市	32
批次	25
科类	5
院校	2232, 省市 2230
更名	679
无计划	54

考生
	234257	[1]文科综合
	373210	[5]理科综合

计划	588634

	75991		[1]本科一批

		13848	[1]文科综合
		62143	[5]理科综合

	190112		[2]本科二批

		60550	[1]文科综合
		129562	[5]理科综合

	190981		[4]高职高专批

		87588	[1]文科综合
		103393	[5]理科综合

	6637		[8]国家专项计划本科批

		1079	[1]文科综合
		5558	[5]理科综合

	1016		[9]地方专项计划本科批

		275	[1]文科综合
		741	[5]理科综合

	19297		[I]提前批艺术本科A段

		13245	[1]文科综合
		2398	[5]理科综合
		3654	[9]文理综合

	4085		[G]提前批体育本科

		1717	[1]文科综合
		2368	[5]理科综合

	2214		[E]提前批普通本科

		424	[1]文科综合
		1790	[5]理科综合

	10033		[J]提前批艺术本科B段

		8032	[1]文科综合
		1970	[5]理科综合
		31	[9]文理综合

	146		[M]提前批司法本科

		64	[1]文科综合
		82	[5]理科综合

	17371		[K]提前批艺术专科

		12971	[1]文科综合
		4400	[5]理科综合

	1545		[B]专科提前批直招士官

		339	[1]文科综合
		1206	[5]理科综合

	340		[F]专科提前批航海

		130	[1]文科综合
		210	[5]理科综合

	953		[L]专科提前批空乘等

		629	[1]文科综合
		324	[5]理科综合

	43908		[Z]专升本批

		43908	[B]专升本

	3554		[X]对口生本科批

		3554	[A]对口生

	16772		[Y]对口生专科批

		16772	[A]对口生

	1009		[H]提前批体育专科

		533	[1]文科综合
		476	[5]理科综合

	1272		[C]提前批公安本科

		360	[1]文科综合
		912	[5]理科综合

	420		[N]提前批司法专科

		269	[1]文科综合
		151	[5]理科综合

	45		[D]提前批公安专科

		24	[1]文科综合
		21	[5]理科综合

	778		[A]提前批军队本科

		25	[1]文科综合
		753	[5]理科综合

	155		[S]提前批军队招飞

		25	[1]文科综合
		130	[5]理科综合

零计划院校代号

	[I]提前批艺术本科A段

		[9]文理综合
		0001 1100 1115 1160 1260 1270 1330 1365 1470 2255
		3150 4280 9900 9901 9902 9905 9906 9907 9908 9910
		9915 9917 9919 9920 9922 9925 9927 9928 9930 9931
		9935 9936 9938 9940 9941 9945 9948 9949 9951 9952
		9955

	[J]提前批艺术本科B段

		[9]文理综合
		9930
```

备注:

	官方地址中按省市查询的院校总数与全部院校总数不符

# TODO

 1. gh-pages 分支
 2. 一个长图表囊括所有重要信息, 左文右理, 中间是分数段

# License

Apache License 2.0 Copyright 2017 @[YU HengChun](https://github.com/achun)