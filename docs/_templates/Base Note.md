---
<%*
let title = tp.file.title;
if (title.startsWith("Untitled")) { title = await tp.system.prompt("Title"); await tp.file.rename(title); }
let author = await tp.system.prompt("Author") || "@anonimus";
let componentInput = await tp.system.suggester(["Networking"], ["Networking"]) || "general";
let tagsInput = await tp.system.prompt("Enter the tags (separated by commas)");
let tags = tagsInput
    .split(",")
    .map(t => t.trim())
    .filter(t => t.length > 0);
tags.push(componentInput);
%>
title: <% title %>
component: <% componentInput %>
status: draft
created by: <% author %>
updated by: <% author %>
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
tags: <% JSON.stringify(tags) %>
---
