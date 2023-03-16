match (n) DETACH DELETE n;

create (s:Student {name: "Tim"});
create (s:Student {name: "Bob"});
create (s:Student {name: "Anja"});

create (s:Subject {name: "WebDev"});
create (s:Subject {name: "ICC"});
create (s:Subject {name: "AWS"});
create (s:Subject {name: "English"});

create (p:Professor {name: "Müller"});
create (p:Professor {name: "Mayer"});
create (p:Professor {name: "Völlinger"});

// profs

MATCH (a), (b)
WHERE a.name = 'WebDev' AND b.name = 'Müller'
CREATE (b)-[r:teaches]->(a);

MATCH (a), (b)
WHERE a.name = 'ICC' AND b.name = 'Mayer'
CREATE (b)-[r:teaches]->(a);

MATCH (a), (b)
WHERE a.name = 'AWS' AND b.name = 'Völlinger'
CREATE (b)-[r:teaches]->(a);

MATCH (a), (b)
WHERE a.name = 'English' AND b.name = 'Völlinger'
CREATE (b)-[r:teaches]->(a);

// students <> fächer

MATCH (a), (b)
WHERE a.name = 'Tim' AND b.name = 'WebDev'
CREATE (a)-[r:enrolled]->(b);

MATCH (a), (b)
WHERE a.name = 'Tim' AND b.name = 'English'
CREATE (a)-[r:enrolled]->(b);

MATCH (a), (b)
WHERE a.name = 'Tim' AND b.name = 'ICC'
CREATE (a)-[r:enrolled]->(b);

MATCH (a), (b)
WHERE a.name = 'Bob' AND b.name = 'ICC'
CREATE (a)-[r:enrolled]->(b);

MATCH (a), (b)
WHERE a.name = 'Bob' AND b.name = 'AWS'
CREATE (a)-[r:enrolled]->(b);

MATCH (a), (b)
WHERE a.name = 'Anja' AND b.name = 'AWS'
CREATE (a)-[r:enrolled]->(b);

MATCH (a), (b)
WHERE a.name = 'Anja' AND b.name = 'English'
CREATE (a)-[r:enrolled]->(b);
