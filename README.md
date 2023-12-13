# PeopleCompetition

我们的代码分为了几个步骤，首先是数据的预处理，放在了dataProcess文件夹，运行generate_adj.py文件可以产生接下来需要的people.mat文件
GNNs程序是社区划分的主程序，在这是我们输出并保存了划分结果，我们采用了GNNs作为模型，由于GNNs有较好的适应性，对于社区的划分是基于设定最大社区数量的软划分（不会强制产生最大数量的社区，在设置最大社区数量为2080时，GNNs的划分结果是产生了实际数量为32的社区划分）
![98551b73d03395852b1e9c7f3da099c6](https://github.com/Superbia-X/PeopleCompetition/assets/58381321/6ad06017-e6c6-4b74-bd1f-d600d3fed720)
为此我们采用了leiden算法来寻找一个合适的最大社区数量，GNNs.py中nums_initials_GNNs_configs 是重复寻最优解的次数
![89850bd07011faafb96c08918453c176](https://github.com/Superbia-X/PeopleCompetition/assets/58381321/77ff4988-ad7f-46bd-82f5-a912ce368951)
为了避免随机性的影响我们设置为2500轮，这可能需要较长的运行时间。
![385ffe4802e0563aef957a9b8733bf7c](https://github.com/Superbia-X/PeopleCompetition/assets/58381321/7f8a4ab9-68c3-46af-9da6-1e8c857cf887)
划分结果将会保存在submission文件夹中，是以最大社区数量-nums_initials_GNNs_configs-num_runs为命名的npy文件，我们在output_to_json.py文件中对该文件进行了转化，将其转化为符合提交格式的submission.json
check_community.py是格式校验文件，可以在提交前进行格式检测

最后是我们的运行环境：

cdlib                     0.3.0

leidenalg                 0.10.1

networkx                  3.2.1

numpy                     1.26.2

python                    3.9.18

python-igraph             0.11.3

scipy                     1.11.4

torch                     2.1.1+cu118              

torchaudio                2.1.1+cu118              

torchvision               0.16.1+cu118             

pycombo                   0.1.7 

pandas                    2.1.3

scikit-learn              1.3.2  

python-louvain            0.16



