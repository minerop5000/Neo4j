match (n) DETACH DELETE n;

create (s:Student {name: "Tim"});
create (s:Student {name: "Bob"});
create (s:Student {name: "Anja"});

create (s:Fach {name: "WebDev"});
create (s:Fach {name: "ICC"});
create (s:Fach {name: "AWS"});

create (p:Prof {name: "Müller"});
create (p:Prof {name: "Mayer"});
create (p:Prof {name: "Völlinger"});

// profs
MATCH (a), (b)
WHERE a.name = 'WebDev' AND b.name = 'Müller'
CREATE (b)-[r:Unterrichtet]->(a);

MATCH (a), (b)
WHERE a.name = 'ICC' AND b.name = 'Mayer'
CREATE (b)-[r:Unterrichtet]->(a);

MATCH (a), (b)
WHERE a.name = 'AWS' AND b.name = 'Völlinger'
CREATE (b)-[r:Unterrichtet]->(a);

// students <> fächer
MATCH (a), (b)
WHERE a.name = 'Tim' AND b.name = 'WebDev'
CREATE (a)-[r:ist_in]->(b);

MATCH (a), (b)
WHERE a.name = 'Tim' AND b.name = 'ICC'
CREATE (a)-[r:ist_in]->(b);

MATCH (a), (b)
WHERE a.name = 'Bob' AND b.name = 'ICC'
CREATE (a)-[r:ist_in]->(b);

MATCH (a), (b)
WHERE a.name = 'Bob' AND b.name = 'AWS'
CREATE (a)-[r:ist_in]->(b);

MATCH (a), (b)
WHERE a.name = 'Anja' AND b.name = 'AWS'
CREATE (a)-[r:ist_in]->(b);
