
# Weaviate
### An Open Source Neural Search Engine & A Vector Database

![Weaviate](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/weaviate-cover.png)

<br>
In today’s digitalized world, search engines have become one of the most powerful tools on the internet and an essential part of our daily lives. By consolidating and organizing the wealth of information available online, search engines like Google, Yahoo, or Bing help billions of online users find the content they need at a rapid pace. Almost 30 percent of global web traffic is generated via online search usage, showing the vital role these platforms play in directing and navigating user flows to different websites. As search engines rank search results in order of relevancy, meaning that the most valuable links for users’ queries are displayed prominently on the results page, high rankings have become one of the top digital priorities for companies worldwide.

<br>
<br>

Summary of todays article
- What is keyword-based searching 
- What is Neural Searching
- Intro to Weaviate; Vector Search Engine
- Weaviate architecture
- Weavite Modules and Custome Modules
- Use cases of weaviate

## What is Keyword-based searching

The most straight forward way of searching is keyword-based searching. What it does is matching the query with the keywords which already have and output the best result. But this approach is fragile as there are multiple way of describing the same data object. Another drawback of this approach is the **polysemy** which means that the same word can have multiple meanings.

Back in 2015 tech giant Google launched **RankBrain** which combines AI to bring a revolution in keyword-based search. 

#### Before RankBrain, process was something like this.
<br>

![Before RankBrain](https://api.backlinko.com/app/uploads/2017/11/1_2_google-engineers-960x683.webp)

<br>

#### After Introducing RankBrain
<br>

![After Rankbrain](https://api.backlinko.com/app/uploads/2017/11/1_3_rankbrain-process-960x363.webp)

So what RankBrain does,
- Depend on the keyword, RankBrain will increase or decrease the importance of backlinks, content refreshes, domain authority etc.
- Then, it looks at how Google searchers interact with the new search results. If users like the new algorithm better, it stays. If not, RankBrain rolls back the old algorithm.

But since data becoming growing exponentially and people wanted to search through voice, images, videos and interact with voice assistance like siri, cortana, and alexa, engineers wanted to apply AI and Deep Learning techniques in order to achieve these use cases. Thats where the neural search comes in to the picture.

## What is Neural Search

Neural Search is a new approach to retrieving information using neural networks. It uses advance techniques as below to make the search more accurate and scalable.
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

## Weaviate

Weaviate is a vector search engine and vector database. Weaviate uses machine learning to vectorize and store data, and to find answers to natural language queries. With Weaviate you can also bring your custom ML models to production scale. 

Additionally Weaviate is a low-latency vector search engine with out-of-the-box support for different media types (text, images, etc.). It offers Semantic Search, Question-Answer Extraction, Classification, Customizable Models (PyTorch/TensorFlow/Keras), and more. Built from scratch in Go, Weaviate stores both objects and vectors, allowing for combining vector search with structured filtering and the fault-tolerance of a cloud-native database, all accessible through GraphQL, REST, and various programming language clients. (Intro from the [documentation](https://weaviate.io/developers/weaviate/current/))

- 80% of the data are unstructured. Hence it is difficult to search and classify data. So adding context and meaning to the data is important. Weaviate focuses on this issue and build a production grade, cloud native, AI based sementic search engine (or vector search engine | neural search engine). 

![weaviate](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/weaviate.png)


I ll expalin the drawback of the tradition search engine by using an example in the documentation.

 ```json
 { "data": "The Eiffel Tower is a wrought iron lattice tower on the Champ de Mars in Paris." }
 ```
 
 Storing this data in a traditional search engine might leverage inverted indices to index the data. This means that to retrieve the data; you need to search for “Eiffel Tower” or “wrought iron lattice”, etc. to find it. But what if you have vast amounts of data and you want the document about the Eiffel Tower but you search for: “landmarks in France”? Traditional search engines can’t help you there and this is where vector search engines show their superiority.

 Weaviate uses vector indexing mechanisms at its core to represent the data. The vectorization modules (e.g., the NLP module) vectorizes the  data object in a vector-space where the data object sits near the search query. This means that Weaviate can’t make a 100% match, but a very high one to show you the results.

 So what is vectorization?

 - It also called word embedding, vector mapping, feature learning
 - Maps the data to vectors of real number.
 - Data Stores in a high dimensional vector space
 - This captures the semantics and relationships between data
 - Data is automatically stored with its meaning
 - Enables automatic classification

 Vector Space

 - each data object has a corresponding vector and position in the vector space.
 - Here data has represented in a 300 long array. That means vector space is 300 dimensional.

 ![vector space](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/vectorSpace.png)

 
 ### High level Architecture of Weaviate

![Higle-level Architecture](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/high-level-weaviate.png)

Refer [this](https://weaviate.io/developers/weaviate/current/architecture/index.html) for more details regarding the architecture. You could find information related to,
- How weaviate store data
- How an inverted index, a vector index and an object store interact with each other
- Learn how combining an HNSW with an inverted index
- ways to scale weaviate
- planning the resources
- Weaviate Modules
- Role of REST and GraphQL APIs,  etc.

I ll walk through the weaviate modules which enables additional functionalities to the vector native database.

### Modules

Weaviate is completely modularized. The functionality of the vector native databse can be enhanced by these modules. There are mainly two types of modules.
1. Dense Retrievers  - These modules vectorize the data. Which means transform the data into vectors. (ex: text2vec-contextionary, text2vec-transformers, text2vec-openai, multi2vec-clip )
2. Reader or Generator modules - These modules add additional functionality. (ex : question answering module, text summarization module). A Reader module takes the set of relevant documents that are retrieved by the Retriever module, and extracts a piece of relevant information per document.  A Generator module would, on the other hand, use language generation to generate an answer from the given document


Typically a (vectorizer) module consists of two parts:

![modules-core](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/modules-core.png)

1. Module code for Weaviate, written in Go, which hooks  into specific lifecycles and provides various capabilities (like controlling the API function) to integrate the module into the regular flow in Weaviate.

    - Tells the Weaviate GraphQL API that the module provides a specific nearText method.
    - Validates specific configuration and schema settings and makes them available to the APIs.
    - Tells Weaviate how to obtain a vector (e.g. a word or image embedding) when one is necessary (by sending an HTTP request to a third-party service, in this case the Python application around the inference model)

2. Inference service, typically a containerized application that wraps an ML model with a module-specific API which is consumed by the module code executed in Weaviate.
    - Provides a service that can do model inference.
    - Implements an API that is in contract with A (not with Weaviate itself).

### Creating a custom module

- Additionaly weaviate allows developers to create custom modules. 
- If the developer comfortable with golang, vector seach engines and with the design of the module, he can start on creating the module.
- In order to design a proper module schema, developer should have an idea about the inference model that he would use and accordingly have to add additional arguments to the module design.

- Example design related to Token classification module

```javascript
{
  Get {
    Article {
      summary
      _additional {
	tokens (
	  properties: ["summary"],
          limit: 2
          certainty: 0.7
	) {
          property
          entity
          certainty
          word
          startPosition   
          endPosition   
        }
      }
    }
  }
}
```
- Result will look like below

```json
{
    "data": {
        "Get": {
            "Article": [
                {
                    "summary": "Shuttered cinemas led them to frantically sell their films to streamers, who were all too ready with outstretched arms and wide-open chequebooks to help bolster their booming business. Watching the splashy animated adventure The Mitchells vs the Machines on Netflix just weeks after Godzilla vs Kong jumpstarted the global box office, one can imagine that some wound-licking might soon be taking place over at Sony, where it was originally envisioned as a big-budget tentpole before being offloaded during the pandemic. It also carries with it a considerable budget, a big bet that belongs on the big screen, instead of launching online after a token one week theatrical window. Sony might be kicking themselves in the immediate future but the millions who will get to see the film on Netflix and the enthusiasm that will surely follow is a sign that its animation arm is doing something special. In the ongoing studios v streamers war, we can call this one a tie.",
                    "_additional": {
                        "tokens": [
                          {
                              "property": "summary",
                              "entity": "MISC",
                              "certainty": 0.9894614815711975,
                              "word": "The Mitchells vs the Machines",
                              "startPosition": 225,
                              "endPosition": 254
                          },
                          {
                              "property": "summary",
                              "entity": "ORG",
                              "certainty": 0.7529033422470093,
                              "word": "Netflix",
                              "startPosition": 258,
                              "endPosition": 265
                          }
                      ]
                  }
                }
            ]
        }
    }
}
```

- Additional properties which have applied for the module design are based on the result which outputs from the inference model. Here [BERT-NER](https://huggingface.co/dslim/bert-base-NER) has used as the inference model. This model returns a result as below.
``` javascript
[
  {
    "entity_group": "PER",
    "score": 0.9964176416397095,
    "word": "Clara",
    "start": 11,
    "end": 16
  },
  {
    "entity_group": "LOC",
    "score": 0.9961979985237122,
    "word": "Berkeley",
    "start": 31,
    "end": 39
  },
  {
    "entity_group": "LOC",
    "score": 0.9990196228027344,
    "word": "California",
    "start": 41,
    "end": 51
  }
]
```
- Hope this make sense with the design. In the design, inside additional property we can see 5 extra arguments as below.
```javascript
{
          entity
          certainty
          word
          start
          end
        }
```
which related to the result from the inference model.
```json
{
    "entity_group": "PER",
    "score": 0.9985478520393372, // certainty
    "word": "Sarah",
    "start": 11,
    "end": 16
  }
```

- Refer below links for more details related to building custom module.

    - [GitHub](https://github.com/semi-technologies/weaviate) 
    - [Custome Module](https://weaviate.io/developers/contributor-guide/current/weaviate-module-system/how-to-build-a-new-module.html)


### Use cases of weaviate

- Currently weaviate support below use cases

![usecase](https://github.com/DasithEdirisinghe/weaviate_doc/blob/main/img/weaviate-usecase.png)

Hope now you have a high level idea about neural search engines and weaviate. Continue on reading more article related to these technologies.

References:
- https://weaviate.io/developers/weaviate/current/
- https://dzone.com/articles/what-is-neural-search
- https://analyticsindiamag.com/neural-nets-transforming-the-world-of-search-engines/

- https://huggingface.co/