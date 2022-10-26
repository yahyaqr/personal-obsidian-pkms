---
created: Wednesday, October 26th 2022 - 17.03
updated: Wednesday, October 26th 2022 - 17.03
---
```mermaid
sequenceDiagram
	participant User
	participant Service
	actor A as Alice
	actor B as Bob
	User ->> Service: yo do dis ding
	activate User
	Service-->>User: gotshu
	Note over User,Service: Ini note
	deactivate User
	loop every Hour
	User -->> Service: wassupp
	end
	Note right of User: Prikitiw
	A-->>B: hello
```