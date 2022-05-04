
#  project5
<p align="center">
<p align="center">

</p><br />
Tune the limiting value of N for your machine that gives the best performance relative to thesequential implementation. Compare this empirically optimal N to the valueofstd::thread : : hardware_concurrency()  for your machine.
Tune the limiting value of N for your machine that gives the best performance relative to thesequential implementation. Compare this empirically optimal N to the value
ofstd::thread : : hardware_concurrency()  for your machine.
In a plain text file name README.md explain how you tuned your concurrent algorithm and theresults of your timing tests. This should be around 6-10 paragraphs and include the output of yourfinal run.

std::thread::hardware_concurrency():4
   List Size     Sequential           Sort       Time (s)     Concurrent           Sort       Time (s)
                        min            max        average            min            max        average
   ---------            ---            ---        -------            ---            ---        -------
         600      0.0033278      0.0078906     0.00440646      0.0020936      0.0104325     0.00503756  threadNUm:1speedUp:0.874721
         600      0.0034469      0.0076083     0.00409279      0.0023284      0.0066595     0.00398242  threadNUm:2speedUp:1.02771
         600      0.0035159      0.0051841     0.00431055      0.0023874      0.0054084     0.00361706  threadNUm:3speedUp:1.19173
         600      0.0035598      0.0072355     0.00470531      0.0023095      0.0062763     0.00367324  threadNUm:4speedUp:1.28097
         600      0.0035768      0.0051491     0.00397286      0.0022308      0.0069364     0.00399834  threadNUm:5speedUp:0.993627
         600      0.0035197      0.0044291     0.00399555      0.0026504      0.0045839     0.00364759  threadNUm:6speedUp:1.09539
         600       0.003195      0.0063191     0.00425807      0.0021185      0.0056996     0.00338345  threadNUm:7speedUp:1.2585
         600      0.0035047      0.0066615     0.00474587      0.0019241       0.004765     0.00332276  threadNUm:8speedUp:1.42829
         600      0.0033957      0.0064804     0.00439209      0.0025034      0.0052456     0.00391432  threadNUm:9speedUp:1.12206
        6000       0.161154         1.6714       0.517629      0.0953669        1.84205       0.410748  threadNUm:1speedUp:1.26021
        6000       0.158283       0.172671       0.164197      0.0887501       0.155936       0.122622  threadNUm:2speedUp:1.33905
        6000       0.158589       0.179127        0.17022      0.0768589       0.165887       0.120842  threadNUm:3speedUp:1.40862
        6000        0.16494       0.203691       0.180628       0.114042       0.168955       0.143689  threadNUm:4speedUp:1.25707
        6000        0.16391       0.317572         0.2182       0.101125       0.221713       0.157981  threadNUm:5speedUp:1.38118
        6000       0.182184       0.266041       0.216633       0.100963       0.212501       0.163818  threadNUm:6speedUp:1.3224
        6000       0.205852       0.268227       0.229617       0.105383       0.235441       0.151594  threadNUm:7speedUp:1.51469
        6000       0.198432       0.304357       0.233336      0.0953995       0.254853       0.194684  threadNUm:8speedUp:1.19854
        6000       0.200525       0.305973       0.231417      0.0922243       0.215819       0.154749  threadNUm:9speedUp:1.49543

1.In my machine,the std::thread : : hardware_concurrency() is 4,
2.At first,When I increase the threadNum(N), the speed up will increase.
3.,But ,when the threadNum (N)exceed the hardware_concurrency 4,the speed up will not increase.
4.And I try different input size, it still can not speed up .


5.the output of final run

List Size     Sequential           Sort       Time (s)     Concurrent           Sort       Time (s)
                        min            max        average            min            max        average
   ---------            ---            ---        -------            ---            ---        -------
           1          5e-07        1.8e-06        6.3e-07          5e-07          6e-07        5.2e-07
          10       1.51e-05       2.83e-05      2.029e-05       1.51e-05       2.61e-05      1.976e-05
         100       0.000338      0.0003873     0.00035942      0.0003465      0.0006686     0.00049198
        1000      0.0070361      0.0117847     0.00859401      0.0040241       0.008586     0.00645606
       10000       0.406887       0.467859       0.429359       0.173617       0.322735       0.234474
