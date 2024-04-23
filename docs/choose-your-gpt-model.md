| Provider  | Model                                                   | Excel | Word | Sheets | Docs |
|-----------|---------------------------------------------------------|-------|------|--------|------|
| OpenAI    | babbage-002 (fine-tuned)                                |       |      |        | yes  |
| Anthropic | claude-3-haiku                                          |       | yes  | yes    |      |
| Anthropic | claude-3-opus                                           |       | yes  | yes    |      |
| Anthropic | claude-3-sonnet                                         |       | yes  | yes    |      |
| OpenAI    | davinci-002 (fine-tuned)                                |       |      |        | yes  |
| OpenAI    | gpt-3.5-turbo (0125)                                    | yes   | yes  | yes    | yes  |
| Azure     | gpt-3.5-turbo (0613)                                    | yes   |      | yes    |      |
| OpenAI    | gpt-3.5-turbo (fine-tuned)                              |       |      |        | yes  |
| OpenAI    | gpt-3.5-turbo-instruct                                  |       | yes  | yes    |      |
| Azure     | gpt-4                                                   | yes   |      | yes    |      |
| OpenAI    | gpt-4                                                   | yes   | yes  | yes    | yes  |
| OpenAI    | gpt-4-1106-vision-preview (with GPT_VISION)             | yes   |      | yes    |      |
| Azure     | gpt-4-turbo                                             | yes   |      | yes    |      |
| OpenAI    | gpt-4-turbo                                             | yes   | yes  | yes    | yes  |
| Perplexity| sonar-small-online (with GPT_WEB and Web browsing bulk tool)| yes |   | yes    |      |
| OpenAI    | text-embedding-ada-002 (with GPT_MATCH)                 | yes   |      | yes    |      |



<div>
  <label for="provider-filter">Filter by Provider:</label>
  <select id="provider-filter" onchange="filterTable('provider-filter', 0)">
    <option value="">All</option>
    <option value="OpenAI">OpenAI</option>
    <option value="Anthropic">Anthropic</option>
    <option value="Azure">Azure</option>
    <option value="Perplexity">Perplexity</option>
  </select>
</div>
<div>
  <label for="model-filter">Filter by Model:</label>
  <select id="model-filter" onchange="filterTable('model-filter', 1)">
    <option value="">All</option>
    <option value="babbage-002 (fine-tuned)">babbage-002 (fine-tuned)</option>
    <option value="claude-3-haiku">claude-3-haiku</option>
    <option value="claude-3-opus">claude-3-opus</option>
    <option value="claude-3-sonnet">claude-3-sonnet</option>
    <option value="davinci-002 (fine-tuned)">davinci-002 (fine-tuned)</option>
    <option value="gpt-3.5-turbo (0125)">gpt-3.5-turbo (0125)</option>
    <option value="gpt-3.5-turbo (0613)">gpt-3.5-turbo (0613)</option>
    <option value="gpt-3.5-turbo (fine-tuned)">gpt-3.5-turbo (fine-tuned)</option>
    <option value="gpt-3.5-turbo-instruct">gpt-3.5-turbo-instruct</option>
    <option value="gpt-4">gpt-4</option>
    <option value="gpt-4-1106-vision-preview (with GPT_VISION)">gpt-4-1106-vision-preview (with GPT_VISION)</option>
    <option value="gpt-4-turbo">gpt-4-turbo</option>
    <option value="sonar-small-online (with GPT_WEB and Web browsing bulk tool)">sonar-small-online (with GPT_WEB and Web browsing bulk tool)</option>
    <option value="text-embedding-ada-002 (with GPT_MATCH)">text-embedding-ada-002 (with GPT_MATCH)</option>
  </select>
</div>
<div>
  <label for="usecases-filter">Filter by Use cases:</label>
  <select id="usecases-filter" onchange="filterTable('usecases-filter', 2)">
    <option value="">All</option>
    <option value="Excel">Excel</option>
    <option value="Word">Word</option>
    <option value="Sheets">Sheets</option>
    <option value="Docs">Docs</option>
  </select>
</div>

| Provider  | Model                                                   | Use cases  | Excel | Word | Sheets | Docs |
|-----------|---------------------------------------------------------|------------|-------|------|--------|------|
| OpenAI    | babbage-002 (fine-tuned)                                |            |       |      |        | yes  |
| Anthropic | claude-3-haiku                                          |            |       | yes  | yes    | yes  |
| Anthropic | claude-3-opus                                           |            |       | yes  | yes    | yes  |
| Anthropic | claude-3-sonnet                                         |            |       | yes  | yes    | yes  |
| OpenAI    | davinci-002 (fine-tuned)                                |            |       |      |        | yes  |
| OpenAI    | gpt-3.5-turbo (0125)                                    |            | yes   | yes  | yes    | yes  |
| Azure     | gpt-3.5-turbo (0613)                                    |            | yes   |      | yes    |      |
| OpenAI    | gpt-3.5-turbo (fine-tuned)                              |            |       |      |        | yes  |
| OpenAI    | gpt-3.5-turbo-instruct                                  |            |       | yes  | yes    | yes  |
| Azure     | gpt-4                                                   |            | yes   |      | yes    |      |
| OpenAI    | gpt-4                                                   |            | yes   | yes  | yes    | yes  |
| OpenAI    | gpt-4-1106-vision-preview (with GPT_VISION)             |            | yes   |      | yes    |      |
| Azure     | gpt-4-turbo                                             |            | yes   |      | yes    |      |
| OpenAI    | gpt-4-turbo                                             |            | yes   | yes  | yes    | yes  |
| Perplexity| sonar-small-online (with GPT_WEB and Web browsing bulk tool)|       | yes |      | yes    |      |
| OpenAI    | text-embedding-ada-002 (with GPT_MATCH)                 |            | yes   |      | yes    |      |

<script>
  function filterTable(selectId, columnIndex) {
    const selectElement = document.getElementById(selectId);
    const selectedValue = selectElement.value.toLowerCase();
    const table = document.querySelector('table');
    const rows = table.querySelectorAll('tr');

    rows.forEach(row => {
      const cells = row.querySelectorAll('td');
      if (cells.length > columnIndex && cells[columnIndex].textContent.toLowerCase().includes(selectedValue)) {
        row.style.display = '';
      } else {
        row.style.display = 'none';
      }
    });
  }
</script>
