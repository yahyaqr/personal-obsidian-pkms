---
created: Sunday, October 23rd 2022 - 11.22
updated: Sunday, October 23rd 2022 - 11.22
---

### 📅 Daily Questions
##### 🌜 Last night, after work, I...
- 

##### 🙌 One thing I've excited about right now is...
- 

##### 🚀 One+ thing I plan to accomplish today is...
- [ ] 

##### 👎 One thing I'm struggling with today is...
- 

---
# 📝 Notes
- <% tp.file.cursor() %>

---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc
```