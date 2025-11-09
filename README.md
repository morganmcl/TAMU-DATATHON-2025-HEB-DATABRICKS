# TAMU-DATATHON-2025-HEB-DATABRICKS

Using Databricks, we built an end-to-end semantic search SEO utilizing HEB data to improve customer satisfaction when searching for products. This included leveraging as many as 4 models that Databricks provides, including Databricks models simultaneously, use of Databricks Spark and vector embedding data science techniques, and utilizing Databricks demos and documentation. In this endeavor, we were able to use Databricks' efficient method of interfacing custom AI models with data to prune our data and quickly generate vectors that were the core of our product.

Databricks provided essential capabilities in leveraging data for AI that we wouldn’t have been able to complete the project without. In particular, the efficient way that vector embeddings could be generated from imported JSON data provided by H-E-B significantly sped up the design and optimization of our product. I want to contrast with the last time our team attended a hackathon – there we spent ~3 hours setting up a vector database in Llamaindex, while here we spent ~20 minutes linking the model to the JSON and starting to generate embeddings. This pattern of reliability and speed in implementing common operations was an aspect of Databricks we really appreciated.

Another essential feature we took full advantage of was Databricks’ model agnosticity, which let us mix and match like kids in a candy store. We used two of Databricks’ embedding models alongside OpenAI models. In the process, we generated vectors for roughly twenty datasets and, well… accidentally vaporized the full compute allocation of four entire accounts. Worth it. Using multiple models enabled us to optimize the vector embeddings, improving performance by 0.11 points from our original models, which was possible because it didn’t require completely rewriting the code to switch.

A final benefit we extensively leveraged was the ease with which Databricks enabled us to manipulate JSON files, especially in relation to Gen AI. A key part of our project was parsing the provided data in the precise way that maximized effectiveness. This was near trivial because the provided sql interface let us directly change datasets already integrated into AI pipelines.

Here are some more specific technical details on our implementation:
#We used the git ingestion capability to directly get the provided JSON files in the platform, which were then ingested by a serverless data warehouse
#We used the SQL interface to manipulate the provided categories to create an effective aggregate of categories.
#We created serving endpoints and models to make custom embedding approaches, which were then applied to datasets.
#We extensively used the Databricks.vector_search class to interface with vector embeddings, especially to compute (as we learned) L2 similarity scores to queries using similarity_search() – the process that formed the core of our product.
#We used the gen AI capabilities to build simple RAG models that attempted to create better aggregate categories for embedding.
