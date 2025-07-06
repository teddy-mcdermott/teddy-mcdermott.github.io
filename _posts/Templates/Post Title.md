<%*
const date = tp.date.now("YYYY-M-D");
const rawTitle = tp.file.title;
const hyphenatedTitle = rawTitle.trim().replace(/\s+/g, "-");
const newTitle = `${date}-${hyphenatedTitle}`;
await tp.file.rename(newTitle);
%>