![98551b73d03395852b1e9c7f3da099c6](https://github.com/Superbia-X/PeopleCompetition/assets/58381321/6aa4273b-cc4a-48e2-a496-f5c1d850a061)![98551b73d03395852b1e9c7f3da099c6](https://github.com/Superbia-X/PeopleCompetition/assets/58381321/03fa0579-a5bd-499a-a283-9df1be653a16)# PeopleCompetition

我们的代码分为了几个步骤，首先是数据的预处理，放在了dataProcess文件夹，运行generate_adj.py文件可以产生接下来需要的people.mat文件
GNNs程序是社区划分的主程序，在这是我们输出并保存了划分结果，我们采用了GNNs作为模型，由于GNNs有较好的适应性，对于社区的划分是基于设定最大社区数量的软划分（不会强制产生最大数量的社区，在设置最大社区数量为2080时，GNNs的划分结果是产生了实际数量为32的社区划分）
【dict_keys([0, 146, 2, 424, 1135, 906, 880, 1924, 1206, 298, 50, 133, 1289, 329, 1294, 809, 347, 1722, 459, 302, 30, 1049, 26, 2011, 642, 1854, 958, 709, 668, 1934, 1773, 1608])】
为此我们采用了leiden算法来寻找一个合适的最大社区数量，在GNNs里可以设置一些参数，我们已经进行调整，但nums_initials_GNNs_configs 是重复寻最优解的次数，为了避免随机性我们设置为2500轮，这可能需要较长的运行时间。
划分结果将会保存在submission文件夹中，是以最大社区数量-nums_initials_GNNs_configs-num_runs为命名的npy文件，我们在output_to_json.py文件中对该文件进行了转化，将其转化为符合提交格式的submission.json
check_community.py是格式校验文件，可以在提交前进行格式检测
