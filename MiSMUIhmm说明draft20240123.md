![image-20240122205206920](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240122205206920.png)

## 访问

[MiSMui](http://10.8.5.43:8888/)

链接ＣＰＵ校园网，在浏览器地址框中输入　http://10.8.5.43:8888/，即可访问ＭｉＳＭｕｉ的最新发布版本。



## HMM Build

![image-20240122205630667](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240122205630667.png)

1. 根据用户上传的蛋白质序列进行建模。

   操作说明：

   1. 在“Select HMM Module Type”下拉面板中选择“Personal_Protein_Built"，
   2. 单击“Browse”在本地电脑中选择上传待对齐的蛋白质序列文件(.[fasta格式_百度百科 (baidu.com)](https://baike.baidu.com/item/fasta格式/1168511))，
   3. 单击“HMM Build”，系统即进行多序列比对运算，而后生成比对结果所对应的隐马尔可夫模型文件(.hmm)，

   结果说明：

   1. Fasta Data Display

      .fasta格式是一种用于存储蛋白质或核酸序列的文件格式。每条序列记录以分号开头，分号后连接序列名称。Fasta Data Display 成功显示形如下图的文本即说明此步成功完成。

      ![image-20240123152922629](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240123152922629.png)

   2. HMM Data Display 显示隐马尔可夫模型的文本，即说明此步成功完成，可以进入下一步（HMM Search模块）

      ![image-20240123154152645](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240123154152645.png)

2. 使用用户上传的蛋白质家族模型

   1. 在“Select HMM Module Type”下拉面板中选择“Personal_HMM_Module”

   2. 单击“Browse”在本地电脑中选择隐马尔可夫模型文件（.hmm)

      结果说明：

      HMM Data Display 显示隐马尔可夫模型的文本，即说明此步成功完成。

      ![image-20240123152121439](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240123152121439.png)

3. 从公共数据库加载蛋白质家族模型（该功能建设中，对应下拉菜单中的”Public database“）

   目前，可通过在公共数据库中手动下载蛋白质家族模型并通过“Personal_HMM_Module”这一模块实现。

   推荐使用的网站：InterPro

   InterPro是一个整合了多个蛋白质家族分类平台信息的网站，支持按照蛋白质序列、文本以及结构骨架搜索。
   
   通过文本搜索可以很方便地根据名称搜索到
   
   Pfam模型侧重描述蛋白质家族大类中共性的结构域，包含序列数较多，长度较短，通常只覆盖蛋白质全长的一部分；TIGRfam模型侧重描述具有专门功能的蛋白质结构，包含序列数较少，长度较长，通常覆盖整个蛋白质长度。
   
   - Pfam模型的下载
   
     ![image-20240122220930945](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240122220930945.png)

Pfam站点已经关闭，对应模型文件在InterPro直接下载。在侧面板中选择“Curation”，点击”Download“即可下载Pfam模型的.hmm文件；

![image-20240122221439308](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240122221439308.png)

TIGRfam数据库目前由NCBI管理，在NCBIfam下载。单击”View [TIGR编号] in NCBIfam，即转到NCBI的Protein Family Models站点，在Details中找到“HMM Profile”这一栏，点击下载图标即下载TIGRfam模型。

![image-20240122221735770](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240122221735770.png)



## HMMSearch 

1. 加载模型后，在侧边栏选择HMM search

   ![image-20240123104824708](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240123104824708.png)

2. 在Select HMM Module Type:下拉菜单中选择搜寻的生物合成基因簇库，可同时选择多项

   选项说明：

   Select HMM Module Type：

   1. MiSM_archea_genebank

      1. NCBI古菌基因序列数据库所预测的BGC，BiG-FAM下载

   2. MiSM_complete

      1. NCBI细菌数据库所包含的全基因组测序数据，由BiG-FAM提供，包括2020年2月17日以前的数据。2020年2月18日及以后的数据从NCBI直接下载预测得到。

   3. MiSM_draft

      1. NCBI数据库中，由短读法测序得到的组装结果，从NCBI直接下载，Antismash预测得到。2020年2月17日以前的数据由BiG-FAM提供，分为三个部分；2020年2月18日及以后的数据按年份分为若干个部分

   4. MiSM_MiBiG

      MiBiG数据库提供的BGC序列库。

   5. MiSM_Lab_Streptomymces

      实验室菌种库测序数据，由Antismash预测的BGC，以各批次测序日期区分。

   6. MiSM 

      全库搜索（此步骤耗时时间较长）
      
   
   Select E-value to Filter
   
   ​	设置过滤用的E-value，默认为1e-20

​       Select Score to Filter

​	       设置过滤用的比对分数，默认为80

​       Select Module Filter

​               设置模块过滤条件



1. product

​	序列翻译产物，通常为蛋白名

 2. monomer_pairings

    描述NRPS/PKS所识别的底物及在产物中引入的模块

 3. aSDomain

    描述NRPS/PKS结构域



3. 单击 HMM search，即开始搜索流程

   ![image-20240123111120619](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240123111120619.png)

​      

4. 查看结果

   ![image-20240123111932882](C:\Users\zhaol\AppData\Roaming\Typora\typora-user-images\image-20240123111932882.png)

结果说明：

NAS_PATH: 单击链接即可打开对应的antimash结果文件

E-value_full: 全长比对区域的E-value，该值越接近0说明结果越显著，匹配越好；

score_full: 全长比对区域的总得分，该值越高说明匹配越好；

bias_full: 全长比对区域的总偏差罚分，该值越高说明结果越不可信；

E-value: 最佳匹配结构域比对区域的E-value。该值与Evalue_full接近说明全长蛋白与模型匹配，有数量级差异说明匹配结构域仅为全长蛋白的一部分；

score: 最佳匹配结构域比对区域的得分，该值越接近0说明结果越显著，匹配越好；

bias：最佳匹配结构域比对区域的罚分；

exp：

N：基因所处链，1为前导链，-1为后随链

location：基因起始与终止位点，反映核酸序列的长度



