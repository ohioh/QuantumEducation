---
description: '@pennylane: https://pennylane.ai/qml/demos/tutorial_qgrnn.html'
---

# The Quantum Graph Recurrent Neural Network

Video: [https://www.youtube.com/watch?v=YBHzT5V1SzU](https://www.youtube.com/watch?v=YBHzT5V1SzU)

Übersetzung:

@paper [https://arxiv.org/pdf/1909.12264.pdf](https://arxiv.org/pdf/1909.12264.pdf)

Autor: Jack Ceroni. Veröffentlicht: 27. Juli 2020. Zuletzt aktualisiert am: 25 März 2021.

## The Quantum Graph Recurrent Neural Network

Diese Demonstration untersucht Quantengraphen rekurrente neuronale Netze (QGRNN), die das Quantenanalogon eines klassischen Graphen rekurrenten neuronalen Netzes und eine Unterklasse des allgemeineren Quantengraphen neuronalen Netzansatzes sind. Sowohl das QGNN als auch das QGRNN wurden in diesem Papier (2019) vorgestellt.

Die Idee:

Ein Graph ist definiert als eine Menge von Knoten und eine Menge von Kanten ( edges ), die Verbindungen zwischen den Knoten ( nodes ) darstellen. Informationen können in Graphen kodiert werden, indem den Knoten und Kanten Zahlen zugewiesen werden, die wir Gewichte nennen. In der Regel ist es praktisch, sich einen Graphen visuell vorzustellen:

In den letzten Jahren hat das Konzept eines neuronalen Graphen-Netzwerks (GNN) in der Gemeinschaft des maschinellen Lernens viel Aufmerksamkeit erregt. Ein GNN versucht, eine Repräsentation (eine Abbildung von Daten in einen niedrigdimensionalen Vektorraum) eines gegebenen Graphen mit Merkmalsvektoren zu erlernen, die den Knoten und Kanten zugeordnet sind. Jeder der Vektoren in der erlernten Darstellung bewahrt nicht nur die Merkmale, sondern auch die Gesamttopologie des Graphen, d. h. welche Knoten durch Kanten verbunden sind. Das neuronale Netz des Quantengraphen versucht etwas Ähnliches, allerdings für quantenmechanische Merkmale, z. B. für eine Sammlung von Quantenzuständen.

Betrachten wir die Klasse der Qubit-Hamiltonianer, die quadratisch sind, was bedeutet, dass der Hamilton Operator entweder Wechselwirkungen zwischen zwei Qubits oder die Energie der einzelnen Qubits darstellen. Diese Klasse von Hamiltonians wird auf natürliche Weise durch Graphen beschrieben, wobei die Terme zweiter Ordnung zwischen den Qubits den gewichteten Kanten zwischen den Knoten und die Terme erster Ordnung den Knotengewichten entsprechen.

Ein bekanntes Beispiel für einen [quadratischen Hamiltonian](https://www.spektrum.de/lexikon/mathematik/quadratische-hamilton-funktion/9589) ist das [Ising-Modell](https://de.wikipedia.org/wiki/Ising-Modell) mit [transversalem Feld](https://de.wikipedia.org/wiki/Transversalelektromagnetische\_Welle), das wie folgt definiert ist

![](<../../.gitbook/assets/grafik (14).png>)

mit  ![](<../../.gitbook/assets/grafik (11).png>)

In diesem Hamiltonian kann die Menge E, die bestimmt, welche Paare von Qubits ZZ-Wechselwirkungen haben, durch die Menge der Kanten eines Graphen dargestellt werden. Mit den Qubits als Knoten wird dieser Graph als Interaktionsgraph bezeichnet. Die θ(1)-Parameter entsprechen den Kantengewichten und die θ(2)

Parameter entsprechen den Gewichten der Knoten.

Dieses Ergebnis impliziert, dass wir über Quantenschaltungen mit graphentheoretischen Eigenschaften nachdenken können. Erinnern Sie sich, dass der Zeitentwicklungsoperator in Bezug auf einen Hamiltonian H definiert ist als:

![](<../../.gitbook/assets/grafik (4).png>)

So haben wir eine saubere Möglichkeit, quadratische Hamiltonianer in [Einheitsvektoren ](https://de.wikipedia.org/wiki/Einheitsvektor)(Quantenschaltungen) [\[ siehe auch Unitry Transfomration \] ](https://en.wikipedia.org/wiki/Unitary\_transformation\_\(quantum\_mechanics\))[\[@paper "Learningn Unitaries by Gradient Descent \] ](https://arxiv.org/pdf/2001.11897.pdf)umzuwandeln, die dieselbe Entsprechung zu einem Graphen haben. Im Fall des Ising-Hamiltonschen haben wir Folgendes:
