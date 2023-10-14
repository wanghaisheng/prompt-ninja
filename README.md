# prompt-ninja


https://github.com/PlexPt/awesome-chatgpt-prompts-zh 


https://github.com/f/awesome-chatgpt-prompts


https://github.com/MustafaaYilmas/mr-gSEO

https://github.com/wqhadija/online-marketer-chatgpt-prompts

https://github.com/bilalnawaz072/AI-Prompts-200-Ideas




https://github.com/licavalentin/writer-gpt/fork

```
export const contentPrompt = `Write highly detailed and informative paragraphs for {{heading}}, with subpoints including a lot of details, evidence or examples: {{subpoints}}, use these keywords:

{{keywords}}

in the response. Make it a first-person narrative. Add personal insights. Incorporate humor into writing. Include markdown tables and bullet points or numbered list when possible.

respond in markdown, for heading use ## and for subpoints ###
`;

export const outlinePrompt = `
Write a creative outline with these keywords in it {{keywords}}, like the following structure:
Title (should be attention-grabbing, descriptive)
Introduction (introduction should be engaging, hooking the reader, providing context)
Section (It should have a clear and descriptive heading that tells the reader what the section is about)
Subpoints (are smaller, more specific pieces of information that support the main points within a section of a blog post)
Conclusion (should be a brief summary of the main points discussed in the post, as well as a call to action or final thoughts).
FAQ (list of common questions that people often ask about a particular topic or subject)
`;

export const outlineRegeneratePromptSystem = `
you will receive an outline, a selected part of it that you will rewrite, but will keep the same context related to the outline and the format of the selection, only respond with the new rewritten text
`;

export const outlineRegeneratePrompt = `
here is the selection:
{{section}}

here is the outline:
{{outline}}
`;

export const keywordsCommand = `
Please give more related keywords to this list: {{keywords}}, do not repeat the keywords.
`;

export const keywordsSystem = `
you will only respond with list of keywords, they should be separated by comma
`;

export const secondaryKeywordsSystem = `
${keywordsSystem}

Make sure not to include this keywords in the reply: 
{{keywords}}
`;

export const systemPrompt = `
You are a wise expert writer who shares an abundance of detail and information on a topic ranging from high level overviews to niche subtopics all the way down to rarely known small details.  
`;

export const outlineToArraySystemPrompt = `
you will receive an outline pick the all the headings and subpoints respond with json format like this:
[{ heading: "string", subpoints: ["string array", ...] }, ...]
`;
```




give url to infer keywords or input keywords


make outline and ask question 




https://github.com/ruankie/ecrivai/blob/main/ecrivai/prompt_templates.py



```



topic_prompt = PromptTemplate(
        input_variables=["dummy"],
        template="""{dummy}Give me a single, specific topic to write an informative, engaging blog about.
This blog topic must be relevant and appealing to many people so that many readers will want to read about it.
The specific topic can be from a wide range of broader topics like physics, science, engineering, lifestyle, health, learning, teaching, history, technology, cryptocurrency, art, music, sport, business, economics, travel, entertainment, gaming, food, etc.
Only give me the specific topic name after this prompt and nothing else. The topic is:"""
    )

keyword_prompt = PromptTemplate(
        input_variables=["topic"],
        template="Give me a list of 5 keywords that for using in blog about {topic}",
    )

content_prompt = PromptTemplate(
    input_variables=["topic"],
    template="""Write a blog post about: {topic}. 
The blog post should have the following characteristics:
- The style and tone of the blog should be informative. You should write in the first person and use a friendly and engaging voice.
- The length of the blog post should be roughly 600 words.
- The blog must contain these sections: introduction, body, and conclusion.
- Each section should have a clear and catchy heading that summarizes its main point.
- Use subheadings, bullet points, lists, quotes, or other elements to break up the text and make it easier to read.
- You should explain why the topic is relevant and important for the audience, what problem or challenge it addresses, how it can be solved or improved, what benefits or advantages it offers, and what action or step the reader should take next.
- Use relevant keywords strategically throughout the blog post to optimize it for search engines and attract more readers. You should also avoid keyword stuffing or using irrelevant or misleading keywords that do not match the content of the blog post.
- Use a catchy title, a hook sentence, a clear thesis statement, a compelling story or anecdote, a surprising fact or statistic, a relevant question or challenge, a strong conclusion.
- You should use these components to capture the attention of the reader and convey the main message and purpose of the blog
- The output format of the entire blog post must be in Markdown. All headings, bullet points, links, etc. must use proper Markdown syntax
- Start with the title of the blog as a first level Markdown heading
Please follow these instructions carefully and write a high-quality and original blog post about: {topic}.
Start immediately with the content of the blog post:"""
)****
```
