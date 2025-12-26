<script setup>

const apiKey = "sk-G5l4qD9dSDxiLsfpNyrhGCSjT6phqYZr";
const baseURL = "https://api.proxyapi.ru/anthropic";

const response = await fetch(`${baseURL}/v1/messages`, {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'x-api-key': apiKey,
        'anthropic-version': '2023-06-01' // Важно указать версию API
    },
    body: JSON.stringify({
        model: "claude-3-7-sonnet-20250219",
        max_tokens: 1000,
        messages: [
            {
                role: "user",
                content: [
                    {
                        type: "text",
                        text: "Какая у тебя модель?"
                    }
                ]
            }
        ]
    })
});

const msg = await response.json();
console.log(msg.content[0].text);


</script>

<template>
    <h3>GPT-5.1-Codex-max</h3>
</template>