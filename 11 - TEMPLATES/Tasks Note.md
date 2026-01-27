---
dg-publish: "true"
tags:
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
dg-note-icon: stone
noteIcon: stone
updated: <% tp.date.now("YYYY-MM-DD HH:mm") %>
dgPassFrontmatter: "true"
---
[[Home|Back home]]
<%* await tp.file.move(`06 - DAILY-WEEKLY TASKS/${tp.file.title}`) %>

Status: [[Stone]]
Tags: [[<% tp.date.now("YYYY-MM") %>]], 

<% tp.file.title %>
<%*
// Template tasks for templater
const tasks = [];

while (true) {

  const t = await tp.system.prompt("New Task (Empty Enter to end the prompt)");

  if (!t) break; // termina se estiver vazio ou cancelar

  tasks.push(`- [ ] ${t}`);

}

-%>

<% tasks.join("\n") %>