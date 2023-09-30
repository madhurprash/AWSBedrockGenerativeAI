# AWSBedrockGenerativeAI

Amazon Bedrock offers access to multiple generative AI models
AWS service enables machine learning innovation on a robust foundation.

The drive to harness the transformative power of high-end machine learning models has meant some businesses are facing new challenges. Teams want assistance in crafting compelling documents, summarizing complex documents, building conversational-AI agents, or generating striking, customized visuals.

Announcing general availability of Amazon Bedrock
Find out about all of the recent updates designed to help even more customers build and scale generative AI applications.
Learn more
In April, Amazon stepped in to assist customers contending with the need to build and scale generative AI applications with a new service: Amazon Bedrock. Bedrock arms developers and businesses with secure, seamless, and scalable access to cutting-edge models from a range of leading companies.

Bedrock provides access to Stability AI’s text-to-image models — including Stable Diffusion, multilingual LLMs from AI21 Labs, and Anthropic’s multilingual LLMs, called Claude and Claude Instant, which excel at conversational and text-processing tasks. Bedrock has been further expanded with the additions of Cohere’s foundation models, as well as Anthropic’s Claude 2 and Stability AI’s Stable Diffusion XL 1.0.

These models, trained on large amounts of data, are increasingly known under the umbrella term foundation models (FMs) — hence the name Bedrock. The abilities of a wide range of FMs — as well as Amazon’s own new FM, called Amazon Titan — are available through Bedrock’s API.


Werner Vogels and Swami Sivasubramanian discuss generative AI
Why gather all these models in one place?

“The world is moving so fast on FMs, it is rather unwise to expect that one model is going to get everything right,” says Amazon senior principal engineer Rama Krishna Sandeep Pokkunuri. “All models come with individual strengths and weaknesses, so our focus is on customer choice.”

Expanding ML access

Bedrock is the latest step in Amazon’s ongoing effort to democratize ML by making it easy for customers to access high-performing FMs, without the large costs inherent in both building those models and maintaining the necessary infrastructure. To that end, the team behind Bedrock is working to enable customers to privately customize that suite of FMs with their own data.

 This digital visualization, created with Stable Diffusion XL, reveals a mesmerizing array of embeddings in the latent space of a machine learning model. Each point represents a unique concept or data point, with lines and colors representing the distances and relationships between points. Together they produce a multidimensional landscape filled with intricate clusters, swirling patterns, and hidden connections.
In this digital visualization, created with Stable Diffusion XL, the latent space of a machine learning model reveals a mesmerizing array of embeddings. It is a multidimensional landscape filled with intricate clusters, swirling patterns, and hidden connections. Each point represents a unique concept or data point. The environment is digital, with lines and colors representing the distances and relationships between embeddings.
“Customers don’t have to stick to our training recipes. We are working to provide a high degree of customizability,” says Bing Xiang, director of applied science at Amazon Web Services' AI Labs.

“For example," Xiang continues, “customers can just point a Titan model at dozens of labeled examples they collected for their use cases and stored in Amazon S3 and fine-tune the model for the specific task.”

Not only is a suite of AI tools offered, it is also meticulously safeguarded. At Amazon, data security is so critical it is often referred to as “job zero”. While Bedrock hosts a growing number of third-party models, those third-party companies never see any customer data. That data, which is encrypted, and the Bedrock-hosted models themselves, remain firmly ensconced on Amazon’s secure servers.

Tackling toxicity

In addition to its commitment to security, Amazon has experience in the LLM arena, having developed a range of proprietary FMs in recent years. Last year, it made its Alexa Teacher Model — a 20-billion-parameter LLM — publicly available. Also last year, Amazon launched Amazon CodeWhisperer, a fully managed service powered by LLMs that can generate reams of robust computer code from natural-language prompts, among other things.

 LLM watermarking.AI.gif
Related content
Responsible AI in the generative era
Continuing in that vein, a standout feature of Bedrock is the availability of Amazon’s Titan FMs, including a generative LLM and an embeddings LLM. Titan FMs are built to help customers grapple with the challenge of toxic content by detecting and removing harmful content in data and filtering model outputs that contain inappropriate content.

When several open-source LLMs burst onto the world stage last year, users quickly realized they could be prompted to generate toxic output, including sexist, racist, and homophobic content. Part of the problem, of course, is that the Internet is awash with such material, so models can absorb some of this toxicity and bias.

Amazon’s extensive investments in responsible AI include the building of guardrails and filters into Titan to ensure the models minimize toxicity, profanity, and other inappropriate behavior. “We are aware that this is a challenging problem, one that will require continuous improvement,” Xiang observed.

 Moschitti.crop.png
Related content
EACL: Language processing at the dawn of the LLM era
To that end, during the Titan models’ development, outputs undergo extensive “red teaming” — a rigorous evaluation process aimed at pinpointing potential vulnerabilities or flaws in a model's design. Amazon even had experts attempt to coax harmful behavior from the models using a variety of tricky text prompts.

“No system of this nature will be perfect, but we're creating Titan with utmost care,” says principal applied scientist Miguel Ballesteros. “We are working towards raising the bar in this field.”

Building Amazon Titan models for efficiency

Creating the Titan models also meant overcoming significant technological challenges, particularly in distributed computing.

“Imagine you are faced with a mathematical problem with four decomposable sub-problems that will take eight hours of solid brain work to complete,” explains Ramesh Nallapati, senior principal applied scientist. “If there were four of you working on it together, how long would it take? Two hours is the intuitive answer, because you are working in parallel.

 Suffix copying.png
Related content
Do large language models really need all those layers?
“That’s not true in the real world, and it’s not true in the computing world,” Nallapati continues. “Why? Because communication time between parties and time for aggregating solutions from sub-problems must be factored in.”

In order to make the distributed computing efficient and cost effective, Amazon has developed both AWS Trainium accelerators — designed mainly for high-performance training of generative AI models, including large language models — and AWS Inferentia accelerators that power its models in operation. Both of these specialized accelerators offer higher throughput and lower cost per inference than comparable Amazon EC2 instances.

These accelerators need to constantly communicate and synchronize during training. To streamline this communication, the team employs 3-D parallelism. Here, three elements — parallelizing data mini-batches, parallelizing model parameters, and pipelining layer-wise computations across these accelerators — are distributed across hardware resources to varying degrees.

“Deciding on the combination of these three axes determines how we use the accelerators effectively,” says Nallapati.

Titan’s training task is further complicated by the fact that accelerators, like all sophisticated hardware, occasionally fail. “Using as many accelerators as we do, it is a question of days or weeks, but one of them is going to fail, and there’s a risk the whole thing is going to come down fast,” says Pokkunuri.

To tackle this reality, the team is pioneering ground-breaking techniques in resilience and fault tolerance in distributed computing.

Efficiency is critical in FMs — both for bottom-line considerations and from a sustainability standpoint, because FMs require immense power, both in training and in operation.

“Inferentia and Trainium are big strategic efforts to make sure our customers get the best cost performance,” says Pokkunuri.

Retrieval-augmented generation

Using Bedrock to efficiently combine the complementary abilities of the Titan models also puts the building blocks of a particularly useful process at a customer’s disposal, via a form of retrieval-augmented generation (RAG).

RAG can address a significant shortcoming in standalone LLMs — they cannot account for new events. GPT-4, for example, trained on information up to 2021, can only tell you that “the most significant recent Russian military action in Ukraine was in 2014”.

 This graphic shows embeddings of text phrases in a representational space, a question "who won the 2022 world cup" and two answers "Messi secures first World Cup after extra-time drama" and "France wins in highest-scoring World Cup final since 1996" are linked to dots in the space, the Messi answer is closer to the question
Embedding news reports in a representational space enables the retrieval of information added since the last update to an LLM; the LLM can then leverage that information to generate text responses to queries (e.g., "Who won the 2022 World Cup?").
It is a massive and expensive undertaking to retrain huge LLMs, with the process itself taking months. RAG provides a way to both incorporate new content into LLMs’ outputs in-between re-trainings and provide a cost-effective way to leverage the power of LLMs on proprietary data.

For example, let’s say you run a big news or financial organization, and you want to use an LLM to intelligently interrogate your entire corpus of news or financial reports, which includes up-to-date knowledge.

“You will be able to use Titan models to generate text based on your proprietary content,” explains Ballesteros. “The Titan embeddings model helps to find documents that are relevant to the prompts. Then, the Titan generative model can leverage those documents as well as the information it has learned during training to generate text responses to the prompts. This allows customers to rapidly digest and query their own data sources.”

A commitment to responsible AI

In April, select Amazon customers were given access to Bedrock, to evaluate the service and provide feedback. Pokkunuri stresses the importance of this feedback: “We are not just trying to meet the bar here — we are trying to raise it. We’re looking to give our customers a delightful experience, to make sure their expectations are being met with this suite of models.”

The stepped launch of Bedrock also underscores Amazon's commitment to responsible AI, says Xiang. “This is a very powerful service, and our commitment to responsible AI is paramount.”

As the number of powerful FMs grows, expect Amazon’s Bedrock to grow in tandem, with an expanding roster of leading third-party models and more exclusive models from Amazon itself.

“Generative AI has evolved rapidly in the past few years, but it’s still in its early stage and has a huge potential,” says Xiang. “We are excited about the opportunity of putting Bedrock in the hands of our customers and helping to solve a variety of problems they are facing today and tomorrow.”

 View from space of a connected network around planet Earth representing the Internet of Things.
