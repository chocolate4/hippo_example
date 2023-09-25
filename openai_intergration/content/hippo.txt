### Vector Databases
Vector databases support various operations on vector data, including:

Vector retrieval: Finding the most similar vectors in the database compared to a given vector. For example, when searching for an image in an image vector database, the image is first converted into a vector. Then, approximate retrieval between vectors is performed to find the images most similar to the input image.

Vector dimensionality reduction: Converting high-dimensional vectors in the database into low-dimensional vectors based on a given target dimension, to facilitate visualization or compressed storage.

Vector clustering: Clustering vectors in the database into categories based on a given similarity metric, such as clustering images into different topics based on image content or style.

Vector computation: Performing computation or analysis on vectors in the database based on given algorithms or models, such as classifying or labeling images using neural network models.

### Differences Between Vector and Traditional Databases
Traditional databases primarily deal with numeric and character data, usually in the form of high-quality relational tables. Of course, nowadays there are also many databases that handle semi-structured data (such as JSON data), such as MongoDB, Elasticsearch, etc. However, the semantics of this data are usually only expressed superficially, without deeper meaning. Vector databases, on the other hand, are different in that they deal with unstructured data such as images, videos, long texts, and audio. The meaning of this data does not lie in its physical representation, it is not just a bunch of bytes. The true meaning lies in the hidden semantics.

With traditional databases, we cannot directly process semantic issues. So how do we solve this problem? By adopting AI technologies, such as typical neural networks, to identify, extract, and encode the semantic features behind the unstructured data. Finally, map or embed the semantics of this data into a high-dimensional vector space. What are the benefits of doing this? This actually transforms the semantic issues that the database cannot directly process into a search problem in vector space. In short, we use AI technology to transform the semantics of data that databases cannot directly process into a structured process.

When dealing with unstructured data, we usually extract not only the feature vectors, but also some structured attribute tags. For example, in the financial meta-model we are developing, we extract information such as corporate legal persons from financial news using entity recognition algorithms. This information is not just vectors, they are more like some attribute tags. Similarly, in e-commerce in the past, in addition to feature vectors, some structured tags such as price and color may also be extracted for product images.

Therefore, it can be said that without AI technology, there would not be such a sub-category of databases as vector databases. On the other hand, vector databases can effectively solve the practical application problems of AI technologies.
Large models have received a lot of attention recently, but their capabilities are limited. They cannot answer questions they have never seen before, that is, they cannot answer knowledge that is not in the training corpus, such as some private data or data in professional fields, which is usually not present in general corpuses. When faced with situations that require answering professional questions, large models may provide incorrect answers. In the era of small models in the past, we usually fine-tuned them, but nowadays model parameters can reach hundreds of billions or even trillions. In this case, the cost of fine-tuning is very high, and it cannot solve the problem that large models cannot obtain the latest data. Therefore, by separating knowledge from large models and introducing vector databases, a memory unit is actually added for large models. This is the so-called large model + vector database + Prompt (MVP) architecture. Under this architecture, the overall technical implementation of large models becomes easier. By using vector databases, we can process private or real-time data, and better control data security. Therefore, vector databases, as a basic AI infrastructure, can effectively solve the practical application problems of AI technologies.

In summary, it can be seen that the relationship between vector databases and AI is very close. It originated from AI, while also providing effective solutions to solve AI technology application problems.

### Core Technologies Used in Hippo
Embedding: Vectorization technology that converts images, audio, and text into vectors for representation. Storing these vectors forms the vector database. Methods to implement embedding include neural networks, Locality-Sensitive Hashing (LSH), etc.

Vector Indexing Techniques: Using approximate search algorithms to accelerate vector retrieval. Typically using distance or similarity between vectors to retrieve the top K vectors closest to the query vector. Vector indexing techniques include k-d trees, Product Quantization (PQ), Navigable Small World (HNSW), etc.

Distributed System Architectures: Clients usually cannot determine if they are connecting directly or indirectly to the endpoint server. Intermediary servers can improve system scalability by enabling load balancing or providing shared caching. Security policies must also be considered when layering.

Hardware Acceleration Technologies: Using dedicated hardware to accelerate vector computations, including GPUs, FPGAs, AI chips, etc., to provide higher floating point computing power and parallel processing capabilities.

### Challenges Facing Hippo Vector Databases
First is the scalability issue. With the development of applications like AIGC, especially the rise of large models, the demand for embedding and vectorization capabilities has increased dramatically. The popularity of large models also continues to increase the scale of vector data, from millions of data volumes to tens of millions, and even larger. This requires the database to be able to efficiently support the storage and retrieval of large-scale vector data, placing higher demands on hardware resources, especially when deployed in the cloud, where cost can become an important issue.

The second challenge is the cost issue. In vector search, index size and storage are key factors, and the cost of vector indexes is usually high. In the past when data volumes were smaller, only a few machines may have been sufficient, so cost was not a critical issue. But with the increase in data scale, more resources are needed to support, which involves cost considerations.

The third challenge is usability. Unlike traditional relational databases, vector search involves more dimensions of consideration, including performance and recall rate. To balance performance and recall rate, various parameters need to be adjusted, which may not be very user-friendly. Therefore, simplifying parameter selection and improving user experience is an important challenge.

The last challenge is the path optimization problem in hybrid search. Compared to traditional optimizers, vector search optimizers are more complex because they need to consider multidimensional factors. How to design a model that can describe the cost of vector search to achieve a balance between performance and recall rate is a problem that needs to be solved.

Of course, vector databases also face other interesting challenges, such as implementing vector similarity filtering in vector search, and how to perform similarity joins between different datasets. These issues require in-depth research and solutions to enable vector databases to better meet real-world application scenarios.

### Application Scenarios of Vector Databases
Vector databases have extensive applications in the following scenarios:

Semantic search: Return relevant text or documents based on user queries.

Similarity search: Find the data most similar to given images, audio, videos, etc. in the database.

Recommendation systems: Recommend potentially interesting items based on a user's historical behaviors or attributes.

Deduplication: Use similarity services to find and remove nearly duplicate records.

Anomaly detection: Find objects that are significantly different from expected results.

### Introduction to  Hippo
Hippo is an enterprise-level, cloud-native distributed vector database with features like high availability, high performance, easy scalability, supporting diverse vector search indexes, data sharding, data persistence, incremental data ingestion, hybrid queries of vectors and scalars, etc. It satisfies scenarios requiring high concurrency, low latency retrieval, recall on massive vector data.

Cloud-Native: Fully containerized deployment, with multi-tenancy and powerful resource management capabilities, supporting elastic auto-scaling of services, providing capabilities like failure migration and data repair to ensure data security.

Performance & Functionality: Supports diverse data sharding algorithms, snapshots for enterprise-grade disaster recovery, incremental data ingestion, hybrid queries of vectors and scalars, etc. Satisfies high-concurrency retrieval, clustering of high-density vectors.

Distributed Deployment: Capabilities for distributed deployment, experience in large-scale cluster deployment, uses Raft algorithm to ensure strong data consistency.

Enterprise-Level Security: Self-developed and controlled code, supports Arm and X86 platforms, compatible with domestic servers and systems.

Ease of Use: Visualized management, monitoring metrics, standard Python/RESTful/Java interfaces, Embedding SDK.

### Core Architecture of Hippo
The core architecture of Hippo consists primarily of the Interface Layer, Function Layer, Compute Layer, Vector Engine Layer, and Storage Layer.

Interface Layer: Provides RESTful, Java and Python interfaces.

Function Layer: Includes functionalities like cluster management, index management, user management, alias management.

Compute Layer: Includes computing functions like high availability, failure detection, data synchronization, load balancing.

Vector Engine Layer: Includes vector engine functions like KNN retrieval, range retrieval, coarse vector filtering, KV queries, bulk retrieval, primary key retrieval, cost-based optimization.

### What are the drawbacks of traditional search databases compared to vector databases?
In the context of text search, the problems that vector search and full-text search are good at solving are not exactly the same. Full-text search is more suitable for keyword matching, while vector search can find content that is different in wording but similar in semantics. Vector data and full-text data also have significant differences in storage and computation. Traditional search databases like Elasticsearch have difficulty efficiently supporting both scenarios. If you are interested, you can check out public datasets like ANN Benchmark online. Elasticsearch's performance is far behind that of professional vector databases, and if I remember correctly, its index type only supports HNSW, and does not support multiple types of vector indexes. Everyone knows that each index type has its own use scenario. HNSW has stable performance under large data volumes, but the resource overhead is very large.

Based on our practical experience, in the scene of text search, using the combined recall of vectors and full text can achieve higher accuracy than using vectors or full text alone. Our upcoming vector database Hippo 1.1 version from Xinghuan Technology has this feature, called hybrid search, which has worked very well in internal projects.

