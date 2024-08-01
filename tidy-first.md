---
marp: true
theme: gaia
title: Tidy First?
backgroundColor: white
color: black
footer: Stefan Trenkel | team neusta
style: |
  footer {
    width: 100%;
    text-align: center;
  }
---

<!-- _class: lead --> 
# Kent Beck: Tidy First?

---

#  Kent Beck

- Extreme Programming Explained: Embrace Change (2000)
- Test-Driven Development: By Example (2002)
- Erstunterzeichner des Agilen Manifest (2001)

---

# Was ist "Tidy First?" ?

- A **Personal** Exercise in **Empirical** Software Design
- **Mini-Refactorings** für besseres Software-Design

---

# Zwischenmenschliche Beziehungen

- "Softwaredesign ist eine Übung in zwischenmenschlichen Beziehungen."
- Drei Beziehungen -> drei Bücher
  - Personal -> Tidy First?
  - Entwickler-Team -> ?
  - Alle Stakeholder -> ?

---

# Empirical Software Design

- Spekulatives Design -> erst designen, dann coden
- Reaktives Design -> erst coden, designen nur im Notfall
- Empirisches Design -> irgendwo dazwischen

---

# Tidyings

- Mini-Refactorings / Aufräumereien
- "Aufräumereien sind eine Untermenge der Refactorings."
- "Sie sind niedliche, knuddelige kleine Refactorings, die niemand wirklich hassen kann."
- "Das Refactoring hat ernsthaften Schaden genommen, als Menschen begannen, es zu nutzen, um lange Pausen bei der Feature-Entwicklung zu erklären."

---
# Drei Kapitel

- Tidyings
- Managen
- Theorie

---

<!-- _class: lead --> 
# 15 Tidyings

---

# Guard Clauses

### Ohne Guard

    function double(value) {
        let result = null;
        if (value != null) {
            result = value * 2;
        }
        return result;
    }

---

# Guard Clauses

### Mit Guard

    function double(value) {
      
        if (value == null) {
            return null;
        }

        return value * 2;
    }

---

# Guard Clauses

- Besser lesbar
- Vorbedingungen und eigentliche Berechnung sind entkoppelt
- Mehrfache Returns sind hier ok

// 1996 von Kent Beck eingeführt ("Smalltalk Best Practice Patterns")

---

# Weitere Tidyings

- Toter Code ("Löschen Sie ihn.")
- Beschreibene Konstanten ("Erstellen Sie eine symbolische Konstante.")
- Hilfsroutinen extrahieren
- Redundante Kommentare entfernen

---

# Kohäsionsreihenfolge

- "Ordnen Sie den Code so neu an, dass die zu ändernden Elemente beieinanderstehen."
- Routinen in einer Datei
- Dateien in einem Verzeichnis
- ...

---

<!-- _class: lead --> 
# Managen

---

# Getrenntes Aufräumen

- Niemals Strukturänderungen und Verhaltensänderungen verschmischen
- Ein Tidying nach dem anderen 

---

# Batchgröße / Pull Requests

- So klein wie möglich
- Kein Review notwendig
- 5 - 60 min

---

# Wann aufräumen?

- Tidy first
- Tidy after
- Tidy later
- Tidy never

---

<!-- _class: lead -->
# Theorie

---

# Der Wert Software

"Software schafft auf zwei Arten Werte:"

- "Was sie heute tut."
- "Die Möglichkeit neuer Dinge, die wir morgen tun können."

---

# Optionalität

- "Optionen sind die ökonomische Magie von Software."
- Optionalität ist der Grund für Strukturänderungen.
- "Strukturänderungen und Verhaltensänderungen [sind] zwei Wege [...] mit denen Werte geschaffen werden."

---

# Kosten von Software

**Constantines Äquivalenz**

- Kosten(Software) ~= Kopplung

// Larry Constantine, Edward Yourdon: "Structured Design" (1975)

---

# Herleitung


// Anfangskosten sind klein
**=> Kosten(Software) ~= Kosten(Änderung)**

// Kosten(kleine Änderungen) << Kosten(große Änderungen)
// Exponential-Verteilung 
**=> Kosten(Software) ~= Kosten(große Änderungen)**

// Große Änderungen sind kaskadierend
**=> Kosten(Software) ~= Kopplung**

---

# Kopplung und Kohäsion

- Hohe Kohäsion, geringe Kopplung

---

# Fazit

- Refactoring des Refactoring
- Leichtgewichtig
- Im Idealfall: Kaskadierend

---

<!-- _class: lead -->
# Vielen Dank!





