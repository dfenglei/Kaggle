# Kaggle


Chinese

Start the server a little differently, still from the `stanford-corenlp-full-2018-02-27 directory:

java -Xmx4g -cp "*" edu.stanford.nlp.pipeline.StanfordCoreNLPServer \
-serverProperties StanfordCoreNLP-chinese.properties \
-preload tokenize,ssplit,pos,lemma,ner,parse \
-status_port 9001  -port 9001 -timeout 15000
In Python:

>>> parser = CoreNLPParser('http://localhost:9001')
>>> list(parser.tokenize(u'我家没有电脑。'))
['我家', '没有', '电脑', '。']

>>> list(parser.parse(parser.tokenize(u'我家没有电脑。')))
[Tree('ROOT', [Tree('IP', [Tree('IP', [Tree('NP', [Tree('NN', ['我家'])]), Tree('VP', [Tree
