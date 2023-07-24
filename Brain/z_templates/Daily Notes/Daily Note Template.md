---
created: <% tp.file.creation_date() %>
---
tags:: [[+Daily Notes]]

# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

<< [[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd').subtract(1, 'd').format('YYYY-MM-DD-dddd') %>|Yesterday]] | [[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd').add(1, 'd').format('YYYY-MM-DD-dddd') %>|Tomorrow]] >>

 - - -
### 😎 Breve descripción del día anterior a las {{Time}}



---
### 🧠 Hobbies

##### Juegos
```text-progress-bar
Progreso read:0/10
```

##### Dibujo
```text-progress-bar
Progreso read:0/10
```

##### Desarrollo
```text-progress-bar
Bead:0/10
```

##### Música
```text-progress-bar
Boad:0/10
```

##### Escritura (Ficción y Ensayos)
```text-progress-bar
B:0/10
```

##### D&D
```text-progress-bar
Progreso read:0/10
```

##### Proyecto Temporal
```text-progress-bar
B:0/10
```

---
### Notes created today
```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc
```

### Notes last touched today
```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc
```