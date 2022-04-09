
## Weaviate
An Open Source Neural Search Engine & A Vector DataBase

<br>

Before dive into the neural search engines, will look in to regular **keyword-based searching**
## What is a Keyword-based searching

The most straight forward way of searching is keyword-based searching. What it does is matching the query with the keywords which we have and output the results. But this approach is brital as there are multiple way of describing the same thing. Other drawback of this approach is the **polysemy** which means that the same word can mean multiple things.
Back in 2015 tech giant Google launched **RankBrain** which combines AI to bring a revolution in keyword-based search. 

#### Before RankBrain process was something like this.
<br>

![Before RankBrain](https://api.backlinko.com/app/uploads/2017/11/1_2_google-engineers-960x683.webp)

<br>

#### After Introducing RankBrain
<br>

![After Rankbrain](https://api.backlinko.com/app/uploads/2017/11/1_3_rankbrain-process-960x363.webp)

So what RankBrain does,
- Depend on the keyword RankBrain will increase or decrease the importance of backlinks, content refreshes, domain authority etc.
- Then, it looks at how Google searchers interact with the new search results. If users like the new algorithm better, it stays. If not, RankBrain rolls back the old algorithm.

But since data becoming growing exponentially and people wanted to search through voice, images, videos and interact with voice assistance like siri, cortana, and alexa, engineers wanted to apply AI and Deep Learning techniques in order to achieve these use cases. Thats where the neural search comes in to the picture.

## What is Neural Search

Neural Search is a new approach to retrieving information using neural networks. It uses advance techniques to make the search more accurate and scalable.
- Use of word embeddings to capture semantic properties of words
- Focus on end-to-end learning of higher-level tasks (e.g., question answering, text summarization)

Applications of Neural Search are,
- Sementic search
- Search between data types
- Search with multiple data types

Typical Process of a neural search engine
1. Index Flow - the AI model stores datasets in the form of searchable indexes with the help of an encoder neural network

<br>

![Index Flow](https://lh5.googleusercontent.com/m0Oq5-zzT5xb-2dyuxIl19o7HPsPBkI1ZYbFoD97yd7RgskpbTWkYCilrcR4VAnQH0x27tu_zr-Xjd_gKsX1mghDO8hmZNsH6nGrptGrbkEz_N93OuzEGgjrqcpeHyTxhgRT-mKL)

<br>

2. Query Flow - the user inputs his query in the form of a document. The AI then uses neural networks to identify the query and then comes up with a list of results based on a similarity score within the input embeddings by using a matching algorithm.

<br>

![Query Flow](https://lh4.googleusercontent.com/NJnMhpBrp8UWl7pSeuEu9XX8oa7K2paUKuVBergTdX3OqajQl3OPpjCrqasy5h6OLaKSK8ZvTnE66mC4AyjzXhDEHC2WVzKlVouEaWq2bIujNGas-fw5c_zBbtCkeJr2p0RYyCTC)

<br>

How Weaviate comes into the picture?

### Weaviate

Weaviate is a vector search engine and vector database. Weaviate uses machine learning to vectorize and store data, and to find answers to natural language queries. With Weaviate you can also bring your custom ML models to production scale. (Intro from the [documentation](https://weaviate.io/developers/weaviate/current/))

- 80% of the data are unstructured and hence it is difficult to search and classify data. So adding context and meaning to the data is important. Weaviate focuses on this issue and build a production grade, cloud native, AI based sementic search engine (or vector search engine | neural search engine). 

![weaviate](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/weaviate.png)


I ll expalin the drawback of tradition search engine by using an example in the documentation.
 - data object: { "data": "The Eiffel Tower is a wrought iron lattice tower on the Champ de Mars in Paris." }
 
 Storing this in a traditional search engine might leverage inverted indices to index the data. This means that to retrieve the data; you need to search for “Eiffel Tower” or “wrought iron lattice”, etc. to find it. But what if you have vast amounts of data and you want the document about the Eiffel Tower but you search for: “landmarks in France”? Traditional search engines can’t help you there and this is where vector search engines show their superiority.

 Weaviate uses vector indexing mechanisms at its core to represent the data. The vectorization modules (e.g., the NLP module) vectorizes the  data object in a vector-space where the data object sits near the search query. This means that Weaviate can’t make a 100% match, but a very high one to show you the results.

 So what is vectorization?

 - It also called word embedding, vector mapping, feature learning
 - Maps the data to vectors of real number.
 - Stores in a high dimensional vector space where
 - This captures the semantics and relationships

 ![vector space](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/vectorSpace.png)




