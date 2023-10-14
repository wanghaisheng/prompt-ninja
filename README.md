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

https://github.com/gcoter/extract-keywords-from-youtube-videos/blob/master/src/extract_keywords_from_description_and_summary.py


```
    extract_keywords_prompt = """
        Title: "{title}"

        Description:
        "{description}"

        Summary of the transcript:
        "{summary}"

        From all of the information above, extract up to 10 keywords (preferably in English).
        Use this format (make sure your output can be read by Python's `json.loads`):

        {{
            "title": "{title}",
            "keywords": ["keyword_1", "keyword_2", ...]
        }}
    """
```



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



blog auto 




https://github.com/convergine/craft-content-buddy/blob/46ec17e97e3de5a7c3c61f9b40859be33ad479c9/src/templates/content/_index.twig#L305

```
        <div class="buddy-spoiler">
            <label>{{ 'promptsCustomize'|t('convergine-contentbuddy') }}</label>
            <div class="buddy-spoiler-content">
                <p>{{ 'promptsCustomizeDescription'|t('convergine-contentbuddy') }}</p>
                <p>{{ 'You can use the following placeholders in your prompts:'|t('convergine-contentbuddy') }}</p>

                <p><code>[[description]]</code> - {{ 'this will be replaced with you article description/topic.'|t('convergine-contentbuddy') }}</p>
                <p><code>[[section]]</code> - {{ 'this will be replaced with the text of generated section.'|t('convergine-contentbuddy') }}</p>
                <p><code>[[text]]</code> - {{ 'this will be replaced with text needed for that prompt.'|t('convergine-contentbuddy') }}</p>
                <p><code>[[section-headlines]]</code> - {{ 'this will be replaced with the suggested headlines for the sections about to be generated.'|t('convergine-contentbuddy') }}</p>
                <p><code>[[keywords]]</code> - {{ 'this will be replaced with the SEO keywords you entered.'|t('convergine-contentbuddy') }}</p>
                <p><code>[[number-of-headlines]]</code> - {{ 'this will be replaced with the number of headlines for the article section.'|t('convergine-contentbuddy') }}</p>
                <p>&nbsp;</p>
                {{ forms.textareaField({
                    label: 'article-title: uses <code>description</code>, <code>section-headlines</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[article-title]',
                    id: 'buddy-prompt-article-title',
                    value: 'Generate a title for an article that discusses the following topic:
[[description]]
The article will include the following sections:
[[section-headlines]]

Title:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:5
                }) }}

                {{ forms.textareaField({
                    label: 'article-title-with-seo-keywords: uses <code>description</code>, <code>section-headlines</code>, <code>keywords</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[article-title-with-seo]',
                    id: 'buddy-prompt-article-title-with-seo',
                    value: 'Generate a title for an article that discusses the following topic:
[[description]]
The article will include the following sections:
[[section-headlines]]
Try to use the following seo keywords when possible: [[keywords]]

Title:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:7
                }) }}

                {{ forms.textareaField({
                    label: 'article-intro: uses <code>description</code>, <code>section-headlines</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[article-intro]',
                    id: 'buddy-prompt-article-intro',
                    value: 'Write an introduction for an article that discusses the following topic:
[[description]]
The article includes the following sections:
[[section-headlines]]

Article Intro:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:6
                }) }}

                {{ forms.textareaField({
                    label: 'article-intro-with-seo-keywords: uses <code>description</code>, <code>section-headlines</code>, <code>keywords</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[article-intro-with-seo]',
                    id: 'buddy-prompt-article-intro-with-seo',
                    value: 'Write an introduction for an article that discusses the following topic:
[[description]]
The article includes the following sections:
[[section-headlines]]
Try to use the following seo keywords when possible: [[keywords]]

Article Intro:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:7
                }) }}

                {{ forms.textareaField({
                    label: 'section-headlines: uses <code>number-of-headlines</code>, <code>description</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section-headlines]',
                    id: 'buddy-prompt-section-headlines',
                    value: 'Suggest a list of [[number-of-headlines]] possible headlines of sections for an article that will cover the following topic:
[[description]]

Section headlines:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:4
                }) }}

                {{ forms.textareaField({
                    label: 'section-headlines-with-seo-keywords: uses <code>number-of-headlines</code>, <code>description</code>, <code>keywords</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section-headlines-with-seo]',
                    id: 'buddy-prompt-section-headlines-with-seo',
                    value: 'Suggest a list of [[number-of-headlines]] possible headlines of sections for an article that will cover the following topic:
[[description]]
Try to use the following seo keywords when possible: [[keywords]]

Section headlines:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:5
                }) }}

                {{ forms.textareaField({
                    label: 'section: uses <code>description</code>, <code>section-headline</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section]',
                    id: 'buddy-prompt-section',
                    value: 'I\'m writing an article about the follow topic:
[[description]]

As part of this article, write a text section that discusses the following: [[section-headline]]

Section body without the title:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:6
                }) }}

                {{ forms.textareaField({
                    label: 'section-with-seo: uses <code>description</code>, <code>section-headline</code>, <code>keywords</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section-with-seo]',
                    id: 'buddy-prompt-section-with-seo',
                    value: 'I\'m writing an article about the follow topic:
[[description]]

As part of this article, write a text section that discusses the following: [[section-headline]]

Try to use the following seo keywords when possible: [[keywords]]

Section body without the title:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:8
                }) }}
                {{ forms.textareaField({
                    label: 'section-with-seo: uses <code>description</code>, <code>section-headline</code>, <code>keywords</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section-with-seo]',
                    id: 'buddy-prompt-section-with-seo',
                    value: 'I\'m writing an article about the follow topic:
[[description]]

As part of this article, write a text section that discusses the following: [[section-headline]]

Try to use the following seo keywords when possible: [[keywords]]

Section body without the title:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:8
                }) }}

                {{ forms.textareaField({
                    label: 'article-conclusion: uses <code>description</code>, <code>section-headlines</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[article-conclusion]',
                    id: 'buddy-prompt-article-conclusion',
                    value: 'Write a conclusion for an article that discusses the following topic:
[[description]]
The article includes the following sections:
[[section-headlines]]

Article conclusion:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:6
                }) }}

                {{ forms.textareaField({
                    label: 'article-conclusion-with-seo: uses <code>description</code>, <code>section-headlines</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[article-conclusion-with-seo]',
                    id: 'buddy-prompt-article-conclusion-with-seo',
                    value: 'Write a conclusion for an article that discusses the following topic:
[[description]]
The article includes the following sections:
[[section-headlines]]
Try to use the following seo keywords when possible: [[keywords]]

Article conclusion:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:7
                }) }}

                {{ forms.textareaField({
                    label: 'image: uses <code>text</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[image]',
                    id: 'buddy-prompt-image',
                    value: 'Describe an image that would be best fit for this text:

 [[text]]

---
Creative image description in one sentence of 6 words:
',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:7
                }) }}

                {{ forms.textareaField({
                    label: 'section-summary: uses <code>section</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section-summary]',
                    id: 'buddy-prompt-section-summary',
                    value: 'Write a short section summary for the following article section text:
[[section]]

Section summary:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:4
                }) }}

                {{ forms.textareaField({
                    label: 'section-summary-with-seo: uses <code>section</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[section-summary-with-seo]',
                    id: 'buddy-prompt-section-summary-with-seo',
                    value: 'Write a short section summary for the following article section text:
[[section]]
Try to use the following seo keywords when possible: [[keywords]]

Section summary:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:5
                }) }}

                {{ forms.textareaField({
                    label: 'tldr: uses <code>text</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[tldr]',
                    id: 'buddy-prompt-tldr',
                    value: 'Write a TL;DR for the following text:
[[text]]

TL;DR:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:4
                }) }}

                {{ forms.textareaField({
                    label: 'tldr-with-seo-keywords: uses <code>text</code>, <code>keywords</code>'|t('convergine-contentbuddy'),
                    name: 'buddy-prompts[tldr-with-seo]',
                    id: 'buddy-prompt-tldr-with-seo',
                    value: 'Write a TL;DR for the following text:
[[text]]
Try to use the following seo keywords when possible: [[keywords]]

TL;DR:',
                    autofocus: true,
                    instructions: '',
                    first: true,
                    placeholder:'',
                    rows:4
                }) }}
```


