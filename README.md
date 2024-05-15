<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">评估中文大语言模型中的幻觉</font></font></h1><a id="user-content-evaluating-hallucinations-in-chinese-large-language-models" class="anchor" aria-label="永久链接：评估中文大语言模型中的幻觉" href="#evaluating-hallucinations-in-chinese-large-language-models"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该存储库包含HalluQA（中文幻觉问答）基准的数据和评估脚本。 HalluQA 的完整数据位于</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">HalluQA.json</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中。介绍HalluQA的论文以及多个中文大语言模型的详细实验结果在</font></font><a href="https://arxiv.org/pdf/2310.03368.pdf" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更新</font></font></h2><a id="user-content-update" class="anchor" aria-label="永久链接：更新" href="#update"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2024.2.28</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> : 我们为 HalluQA 添加多项选择任务。多项选择任务的测试数据位于 HalluQA_mc.json 中。多选QA提示位于prompss/Chinese_QA_prompt_mc.txt中。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据收集管道</font></font></h2><a id="user-content-data-collection-pipeline" class="anchor" aria-label="永久链接：数据收集管道" href="#data-collection-pipeline"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/OpenMOSS/HalluQA/blob/main/imgs/pipeline.png"><img src="/OpenMOSS/HalluQA/raw/main/imgs/pipeline.png" alt="" style="max-width: 100%;"></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
HalluQA包含450个精心设计的对抗性问题，跨越多个领域，并考虑到中国历史文化、习俗和社会现象。数据收集的流程如上所示。在第一步，我们写下我们认为可能引起模型幻觉的问题。在步骤2中，我们使用ChatGPT3.5/Puyu/GLM-130B生成答案并收集对抗性问题。在第 3 步，我们为每个对抗性问题写出多个正确和错误的答案，并添加支持证据。在步骤 4 中，我们检查所有带注释的问答对并删除低质量样本。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据示例</font></font></h2><a id="user-content-data-examples" class="anchor" aria-label="永久链接：数据示例" href="#data-examples"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们在这里展示 HalluQA 的一些数据示例。
</font></font><a target="_blank" rel="noopener noreferrer" href="/OpenMOSS/HalluQA/blob/main/imgs/examples.png"><img src="/OpenMOSS/HalluQA/raw/main/imgs/examples.png" alt="" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">衡量与评估方法</font></font></h2><a id="user-content-metric--evaluation-method" class="anchor" aria-label="永久链接：指标和评估方法" href="#metric--evaluation-method"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们使用非幻觉率作为 HalluQA 的指标，它表示所有模型生成的答案中不表现出幻觉的答案的百分比。</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
对于自动化评估，我们使用 GPT-4 作为评估器。 GPT-4将根据给定的标准和参考正确答案来判断生成的答案是否表现出幻觉。</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
基于GPT-4的评估的提示位于</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">calculate_metrics.py中</font></font></strong></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对您的模型进行评估</font></font></h3><a id="user-content-run-evaluation-for-your-models" class="anchor" aria-label="永久链接：对您的模型进行评估" href="#run-evaluation-for-your-models"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ol dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装要求</font></font></li>
</ol>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>pip install openai
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="pip install openai" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<ol start="2" dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用我们的脚本运行评估。</font></font></li>
</ol>
<div class="highlight highlight-source-python notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-s1">python</span> <span class="pl-s1">calculate_metrics</span>.<span class="pl-s1">py</span> <span class="pl-c1">-</span><span class="pl-c1">-</span><span class="pl-s1">response_file_name</span> <span class="pl-s1">gpt</span><span class="pl-c1">-</span><span class="pl-c1">4</span><span class="pl-c1">-</span><span class="pl-c1">0613_</span><span class="pl-s1">responses</span>.<span class="pl-en">json</span>(<span class="pl-s">"replace with your own responses"</span>) <span class="pl-c1">-</span><span class="pl-c1">-</span><span class="pl-s1">api_key</span> <span class="pl-s">"your openai api key"</span> <span class="pl-c1">-</span><span class="pl-c1">-</span><span class="pl-s1">organization</span> <span class="pl-s">"organization of your openai account"</span></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python calculate_metrics.py --response_file_name gpt-4-0613_responses.json(&quot;replace with your own responses&quot;) --api_key &quot;your openai api key&quot; --organization &quot;organization of your openai account&quot;" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<ol start="3" dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">结果和指标将分别保存在 results.json 和 non_hallucination_rate.txt 中。</font></font></li>
</ol>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">多项选择任务</font></font></h3><a id="user-content-multiple-choice-task" class="anchor" aria-label="永久链接：多项选择任务" href="#multiple-choice-task"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们还为 HalluQA 提供了多项选择任务。您需要首先使用要测试的模型、使用我们的</font></font><a href="/OpenMOSS/HalluQA/blob/main/prompts/Chinese_QA_prompt_mc.txt"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">多项选择提示</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">生成每个问题的答案，然后使用以下脚本计算多项选择任务的准确性。</font></font></p>
<div class="highlight highlight-source-python notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-s1">python</span> <span class="pl-s1">calculate_metrics_mc</span>.<span class="pl-s1">py</span> <span class="pl-c1">-</span><span class="pl-c1">-</span><span class="pl-s1">response_file_name</span> <span class="pl-c1">&lt;</span><span class="pl-s1">your_results_file_name</span><span class="pl-c1">&gt;</span></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python calculate_metrics_mc.py --response_file_name <your_results_file_name>" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">结果</font></font></h2><a id="user-content-results" class="anchor" aria-label="永久链接：结果" href="#results"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">排行榜</font></font></h3><a id="user-content-leaderboard" class="anchor" aria-label="永久链接：排行榜" href="#leaderboard"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">各模型针对不同题型的非幻觉率</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：</font></font></p>
<table>
<thead>
<tr>
<th><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">模型</font></font></strong></th>
<th><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">误导性的</font></font></strong></th>
<th><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">难以误导</font></font></strong></th>
<th><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">知识</font></font></strong></th>
<th><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">全部的</font></font></strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">检索增强聊天模型</font></font></strong></em></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ERNIE-机器人</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">70.86</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">46.38</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">75.73</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">69.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川2-53B</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">59.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">43.48</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">83.98</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">68.22</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ChatGLM-专业版</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">64.00</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">34.78</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">67.96</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">61.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">火花台</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">59.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">27.54</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">71.36</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">60.00</font></font></td>
</tr>
<tr>
<td><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">聊天模型</font></font></strong></em></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">abab5.5-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">60.57</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">39.13</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">57.77</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">56.00</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GPT-4-0613</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">76.00</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">57.97</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">32.04</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">53.11</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Qwen-14B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">75.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">23.19</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">30.58</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">46.89</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川2-13B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">61.71</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">24.64</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">32.04</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">42.44</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川2-7B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">54.86</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">28.99</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">32.52</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">40.67</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GPT-3.5-turbo-0613</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">66.29</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">30.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">19.42</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">39.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xverse-13B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">65.14</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">23.19</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">22.33</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">39.11</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xverse-7B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">64.00</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">13.04</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">21.84</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">36.89</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">聊天GLM2-6B</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">55.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">23.19</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">21.36</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">34.89</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Qwen-7B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">55.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">14.49</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">17.48</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">31.78</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川-13B-聊天</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">49.71</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">8.70</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">23.30</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">31.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">聊天GLM-6b</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">52.57</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">20.29</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">15.05</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">30.44</font></font></td>
</tr>
<tr>
<td><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">预训练模型</font></font></strong></em></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Qwen-14B</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">54.86</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">23.19</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">24.76</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">36.22</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川2-13B-基地</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">23.43</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">24.64</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">45.63</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">33.78</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Qwen-7B</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">48.57</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">20.29</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">16.99</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">29.78</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xverse-13B</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">18.86</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">24.64</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">32.52</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">27.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川13B基地</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">9.71</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">18.84</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">40.78</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">25.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川2-7B-基地</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">8.00</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">21.74</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">41.26</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">25.33</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">百川7B基地</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">6.86</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">15.94</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">37.38</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">22.22</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Xverse-7B</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">12:00</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">13.04</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">29.61</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">20.22</font></font></td>
</tr>
</tbody>
</table>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">详细结果</font></font></h3><a id="user-content-detailed-results" class="anchor" aria-label="永久链接：详细结果" href="#detailed-results"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">每个模型生成的答案以及对应的 GPT-4 判断都在</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Chinese_LLMs_outputs/</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中。</font></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">多项选择任务结果</font></font></h3><a id="user-content-multiple-choice-task-results" class="anchor" aria-label="永久链接：多项选择任务结果" href="#multiple-choice-task-results"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里，我们报告了七个代表性模型的多项选择任务的准确性。
</font></font><a target="_blank" rel="noopener noreferrer" href="/OpenMOSS/HalluQA/blob/main/imgs/mc_acc.png"><img src="/OpenMOSS/HalluQA/raw/main/imgs/mc_acc.png" alt="" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">致谢</font></font></h2><a id="user-content-acknowledgements" class="anchor" aria-label="永久链接：致谢" href="#acknowledgements"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们衷心感谢参与这项工作的上海人工智能实验室的注释者和工作人员。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">特别感谢孙天祥、刘向阳和张文伟的指导和帮助。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我也感谢浦新阳的帮助和耐心。</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">引文</font></font></h2><a id="user-content-citation" class="anchor" aria-label="永久链接：引文" href="#citation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="highlight highlight-text-bibtex notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-k">@article</span>{<span class="pl-en">DBLP:journals/corr/abs-2310-03368</span>,
  <span class="pl-s">author</span>       = <span class="pl-s"><span class="pl-pds">{</span>Qinyuan Cheng and</span>
<span class="pl-s">                  Tianxiang Sun and</span>
<span class="pl-s">                  Wenwei Zhang and</span>
<span class="pl-s">                  Siyin Wang and</span>
<span class="pl-s">                  Xiangyang Liu and</span>
<span class="pl-s">                  Mozhi Zhang and</span>
<span class="pl-s">                  Junliang He and</span>
<span class="pl-s">                  Mianqiu Huang and</span>
<span class="pl-s">                  Zhangyue Yin and</span>
<span class="pl-s">                  Kai Chen and</span>
<span class="pl-s">                  Xipeng Qiu<span class="pl-pds">}</span></span>,
  <span class="pl-s">title</span>        = <span class="pl-s"><span class="pl-pds">{</span>Evaluating Hallucinations in Chinese Large Language Models<span class="pl-pds">}</span></span>,
  <span class="pl-s">journal</span>      = <span class="pl-s"><span class="pl-pds">{</span>CoRR<span class="pl-pds">}</span></span>,
  <span class="pl-s">volume</span>       = <span class="pl-s"><span class="pl-pds">{</span>abs/2310.03368<span class="pl-pds">}</span></span>,
  <span class="pl-s">year</span>         = <span class="pl-s"><span class="pl-pds">{</span>2023<span class="pl-pds">}</span></span>,
  <span class="pl-s">url</span>          = <span class="pl-s"><span class="pl-pds">{</span>https://doi.org/10.48550/arXiv.2310.03368<span class="pl-pds">}</span></span>,
  <span class="pl-s">doi</span>          = <span class="pl-s"><span class="pl-pds">{</span>10.48550/arXiv.2310.03368<span class="pl-pds">}</span></span>,
  <span class="pl-s">eprinttype</span>    = <span class="pl-s"><span class="pl-pds">{</span>arXiv<span class="pl-pds">}</span></span>,
  <span class="pl-s">eprint</span>       = <span class="pl-s"><span class="pl-pds">{</span>2310.03368<span class="pl-pds">}</span></span>,
  <span class="pl-s">timestamp</span>    = <span class="pl-s"><span class="pl-pds">{</span>Thu, 19 Oct 2023 13:12:52 +0200<span class="pl-pds">}</span></span>,
  <span class="pl-s">biburl</span>       = <span class="pl-s"><span class="pl-pds">{</span>https://dblp.org/rec/journals/corr/abs-2310-03368.bib<span class="pl-pds">}</span></span>,
  <span class="pl-s">bibsource</span>    = <span class="pl-s"><span class="pl-pds">{</span>dblp computer science bibliography, https://dblp.org<span class="pl-pds">}</span></span>
}</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="@article{DBLP:journals/corr/abs-2310-03368,
  author       = {Qinyuan Cheng and
                  Tianxiang Sun and
                  Wenwei Zhang and
                  Siyin Wang and
                  Xiangyang Liu and
                  Mozhi Zhang and
                  Junliang He and
                  Mianqiu Huang and
                  Zhangyue Yin and
                  Kai Chen and
                  Xipeng Qiu},
  title        = {Evaluating Hallucinations in Chinese Large Language Models},
  journal      = {CoRR},
  volume       = {abs/2310.03368},
  year         = {2023},
  url          = {https://doi.org/10.48550/arXiv.2310.03368},
  doi          = {10.48550/arXiv.2310.03368},
  eprinttype    = {arXiv},
  eprint       = {2310.03368},
  timestamp    = {Thu, 19 Oct 2023 13:12:52 +0200},
  biburl       = {https://dblp.org/rec/journals/corr/abs-2310-03368.bib},
  bibsource    = {dblp computer science bibliography, https://dblp.org}
}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
</article></div>
