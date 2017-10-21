原创wors2vec算法  
属于atulocher项目的一部分  
使用方法：  
先 `#include "word2vec.hpp"`  
然后  
``` c++
  atulocher::word2vec wv(
    "test.sph",                 //生成的.sph文件
    
    "./dict/jieba.dict.utf8",
    "./dict/hmm_model.utf8",
    "./dict/user.dict.utf8",
    "./dict/idf.utf8",
    "./dict/stop_words.utf8",   //cppjieba的词典
    
    "weighter.txt"
  );
  
  std::string wd="云计算;
  std::list< std::pair<std::string,double> > wdmean;
  wdmean.push_back(std::pair<std::string,double>("云",0.3));
  wdmean.push_back(std::pair<std::string,double>("计算",0.7));
  wv.learn(wd,wdmean);
  
  vec3<double> v=wv.wordToVec("云计算");
```
