# 1
操作过程&结果：

[过程1](https://cloud.tsinghua.edu.cn/smart-link/66e8308a-592e-4b64-a65c-fb042a28ab59/)

[过程2](https://cloud.tsinghua.edu.cn/smart-link/a76c238b-e17a-4a9e-8431-d8638359938b/)

[结果1](https://cloud.tsinghua.edu.cn/smart-link/cf602f09-52e7-4e36-9878-27d2d088976e/)

[结果2](https://cloud.tsinghua.edu.cn/smart-link/22c937aa-0327-4537-92b1-36b104a6ddec/)

> E value：表示在随机序列中会发现与目标序列相似的匹配的期望次数。E值越小，结果是随机产生的可能性越小，匹配更严格
> 
> P value：表示得到的结果的可信度。

# 2
脚本文件：[https://cloud.tsinghua.edu.cn/f/78d3c2d32807427e8c04/?dl=1](https://cloud.tsinghua.edu.cn/f/78d3c2d32807427e8c04/?dl=1)

结果文件：[https://cloud.tsinghua.edu.cn/f/8bf4e1d66a9e416aa7ef/?dl=1](https://cloud.tsinghua.edu.cn/f/8bf4e1d66a9e416aa7ef/?dl=1)

简单版结果：

sequence1	sequence1	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence1	sequence5	83.333	6	1	0	43	48	16	21	1.2	14.6

sequence1	sequence2	43.478	23	10	1	40	62	16	35	4.6	12.7

sequence2	sequence2	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence2	sequence8	83.333	6	1	0	1	6	61	66	3.8	13.1

sequence2	sequence6	80.000	5	1	0	10	14	37	41	8.4	12.3

sequence3	sequence3	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence4	sequence4	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence4	sequence8	87.500	8	1	0	30	37	63	70	0.38	15.8

sequence5	sequence5	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence5	sequence1	80.000	5	1	0	16	20	43	47	9.8	11.9

sequence6	sequence6	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence6	sequence10	71.429	7	2	0	34	40	16	22	5.8	12.7

sequence6	sequence2	80.000	5	1	0	37	41	10	14	8.2	12.3

sequence7	sequence7	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence7	sequence6	100.000	6	0	0	44	49	61	66	1.1	14.6

sequence7	sequence10	70.000	10	3	0	55	64	61	70	3.2	13.5

sequence7	sequence3	46.667	15	8	0	50	64	26	40	8.7	12.3

sequence8	sequence8	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence8	sequence6	40.000	30	18	0	14	43	18	47	0.91	14.6

sequence8	sequence10	57.143	14	6	0	11	24	43	56	2.7	13.5

sequence8	sequence2	83.333	6	1	0	61	66	1	6	5.1	12.7

sequence9	sequence9	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence9	sequence6	75.000	8	2	0	44	51	23	30	5.6	12.7

sequence9	sequence4	45.455	11	6	0	46	56	44	54	8.0	12.3

sequence9	sequence3	31.579	19	13	0	22	40	27	45	8.9	11.9

sequence10	sequence10	100.000	70	0	0	1	70	1	70	2.20e-43	123

sequence10	sequence3	38.095	21	13	0	18	38	15	35	0.48	15.4

sequence10	sequence6	58.333	12	5	0	16	27	34	45	0.65	15.0

对结果的可能解释：多数序列只能跟除自己外的2-3条序列比对上，说明没有任何同源性的随机打乱的序列较难通过blast算法比对成功，但是由于随机性的原因，也有匹配成功的可能。
# 3
* 通过k-mer算法过滤掉不相关的序列，进而降低比对的运算量以提高速度。
* 通过数据库的预先和添加索引，使得搜索过程可以快速定位可能相关的区域，而无需遍历整个数据库，进而减少搜索目标。
* 通过对数据库的分段，增加并行的运算数量。
* 在比对过程中，寻找一些得分较高的片段作为种子序列，以此为基础在周围进行比对，进而舍弃掉一些无用的区域以降低运算量。
# 4
在对称的PAM250矩阵中，氨基酸由A替换为B的概率与由B替换为A的概率相等，在不对称矩阵中则不相等。这意味着在对称矩阵中，氨基酸替换是完全的随机事件，没有方向，而不对称的矩阵则考虑了由于选择压力等原因导致的替换的方向性。因此，对称矩阵适用于广泛的进化分析和蛋白质序列比对，特别是在没有特定进化压力或方向性的假设下。而不对称矩阵适用于对于一些有具体功能或进化方式的基因的分析，特别是在研究特定进化路径、功能约束或非随机进化事件时。
