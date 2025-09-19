分析`app.py` 和`validator.py`可知，本题要求上传代码中所定义的`TextClassifier`文本分类器的`checkpoint`文件，该文件使得分类器将验证集中的所有样本分类错误。
给了训练代码和训练样本，而分类器为二分类器，因此只需要将训练样本中的标签全部取反，并调用训练代码得到`checkpoint`文件，并将`checkpoint`文件上传即可得到 flag。