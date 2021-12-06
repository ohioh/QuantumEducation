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

![](<../../.gitbook/assets/grafik (14) (1).png>)

mit ![](<../../.gitbook/assets/grafik (11) (1).png>)

In diesem Hamiltonian kann die Menge E, die bestimmt, welche Paare von Qubits ZZ-Wechselwirkungen haben, durch die Menge der Kanten eines Graphen dargestellt werden. Mit den Qubits als Knoten wird dieser Graph als Interaktionsgraph bezeichnet. Die θ(1)-Parameter entsprechen den Kantengewichten und die θ(2)

Parameter entsprechen den Gewichten der Knoten.

Dieses Ergebnis impliziert, dass wir über Quantenschaltungen mit graphentheoretischen Eigenschaften nachdenken können. Erinnern Sie sich, dass der Zeitentwicklungsoperator in Bezug auf einen Hamiltonian H definiert ist als:

![](<../../.gitbook/assets/grafik (4) (1).png>)

So haben wir eine saubere Möglichkeit, quadratische Hamiltonianer in [Einheitsvektoren ](https://de.wikipedia.org/wiki/Einheitsvektor)(Quantenschaltungen) [\[ siehe auch Unitry Transfomration \] ](https://en.wikipedia.org/wiki/Unitary\_transformation\_\(quantum\_mechanics\))[\[@paper "Learningn Unitaries by Gradient Descent \] ](https://arxiv.org/pdf/2001.11897.pdf)umzuwandeln, die dieselbe Entsprechung zu einem Graphen haben. Im Fall des Ising-Hamiltonschen haben wir Folgendes:

![](<../../.gitbook/assets/grafik (16).png>)

Im Allgemeinen ist es sehr schwierig, diese Art von Unitarität auf einem Quantencomputer zu implementieren. Wir können sie jedoch mit Hilfe der [Trotter-Suzuki-Zerlegung](https://en.wikipedia.org/wiki/Time-evolving\_block\_decimation#The\_Suzuki-Trotter\_expansion) annähern:

![](<../../.gitbook/assets/grafik (9).png>)

mit ![](<../../.gitbook/assets/grafik (18).png>)ist der j-te Term des Ising-Hamiltonschen und Δ

eine kleine Zahl ist.

Diese Schaltung ist ein spezieller Fall des rekurrenten neuronalen Quantengraphen-Netzwerks, das im Allgemeinen als Variationsansatz der folgenden Form definiert ist:

$$
U_{H}(\boldsymbol\mu, \ \boldsymbol\gamma) \ = \ \displaystyle\prod_{i \ = \ 1}^{P} \Bigg[ \displaystyle\prod_{j \ = \ 1}^{Q} e^{-i \gamma_j H^{j}(\boldsymbol\mu)} \Bigg],
$$

für einen parametrisierten quadratischen Hamiltonian, H(μ)

Verwendung des QGRNN

Da der QGRNN-Ansatz der ungefähren zeitlichen Entwicklung eines quadratischen Hamiltonian entspricht, können wir ihn verwenden, um die Dynamik eines Quantensystems zu erlernen.

Fahren wir mit dem Beispiel des Ising-Modells fort und stellen wir uns vor, wir hätten ein System, das wie folgt gesteuert wird

$$
\hat{H}_{\text{Ising}}(\boldsymbol\alpha)
$$

for an unknown set of target parameters, $$α$$ and an unknown interaction graph $$G$$. Let’s also suppose we have access to copies of some low-energy, non-ground state of the target Hamiltonian,$$|ψ0⟩$$Darüber hinaus haben wir Zugang zu einer Sammlung zeitlich entwickelter Zustände, $$\{ |\psi(t_1)\rangle, \ |\psi(t_2)\rangle, \ ..., \ |\psi(t_N)\rangle \}$$ definiert als:

$$
|\psi(t_k)\rangle \ = \ e^{-i t_k \hat{H}_{\text{Ising}}(\boldsymbol\alpha)} |\psi_0\rangle.
$$

Wir nennen die Zustände mit niedriger Energie und die Sammlung der zeitlich entwickelten Zustände Quantendaten. Von hier aus wählen wir nach dem Zufallsprinzip eine Anzahl zeitlich entwickelter Zustände aus unserer Sammlung aus. Für jeden Zustand, den wir auswählen und der sich zu einem bestimmten Zeitpunkt tk entwickelt hat, vergleichen wir ihn mit

$$
U_{\hat{H}_{\text{Ising}}}(\boldsymbol\mu, \ \Delta) |\psi_0\rangle \ \approx \ e^{-i t_k \hat{H}_{\text{Ising}}(\boldsymbol\mu)} |\psi_0\rangle.
$$

Dazu wird eine der Kopien von |ψ0⟩ in einen Quantenschaltkreis mit dem QGRNN-Ansatz eingespeist, mit einem geschätzten Satz von Parametern μ und einem geschätzten Interaktionsgraphen G′.

Wir verwenden dann einen klassischen Optimierer, um die durchschnittliche "Ähnlichkeit" zwischen den zeitlich entwickelten Zuständen und den mit dem QGRNN vorbereiteten Zuständen zu maximieren.

Da die QGRNN-Zustände jedem zeitlich entwickelten Zustand für jede abgetastete Zeit immer ähnlicher werden, folgt daraus, dass μ → α und wir sind in der Lage, die unbekannten Parameter des Hamiltonian zu lernen.

![](<../../.gitbook/assets/grafik (11).png>)

Eine visuelle Darstellung einer Ausführung des QGRNN für einen Teil der Quantendaten.

## Trannieren eine Ising-Models mit QGRNN

Wir versuchen nun, das QGRNN zu verwenden, um die Parameter zu lernen, die einem beliebigen Hamiltonian des Ising-Modells mit transversalem Feld entsprechen.

## Lets rock the code:

```
import pennylane as qml
from matplotlib import pyplot as plt
from pennylane import numpy as np
import scipy
import networkx as nx
import copy
```

Wir legen auch einige feste Werte fest, die während der gesamten Simulation verwendet werden.

```
qubit_number = 4
qubits = range(qubit_number)
```

In dieser Simulation stehen uns keine Quantendaten zur Verfügung, die wir in das QGRNN einspeisen könnten, also müssen wir sie selbst erzeugen. Dazu müssen wir den Zielwechselwirkungsgraphen und den Ziel-Hamiltonian kennen.

Lassen Sie uns den folgenden zyklischen Graphen als Ziel-Interaktionsgraphen des Ising-Hamiltonianers verwenden:

```
ising_graph = nx.cycle_graph(qubit_number)

print(f"Edges: {ising_graph.edges}")
nx.draw(ising_graph)
```

Dann können wir die "unbekannten" Zielparameter initialisieren, die den Ziel-Hamiltonian beschreiben,$$\boldsymbol\alpha \ = \ \{\alpha^{(1)}, \ \alpha^{(2)}\}$$.Aus der Einleitung wissen wir, dass wir unsere parametrisierte Ising-Hamiltonsche so definiert haben, dass sie die Form hat:

$$
\hat{H}_{\text{Ising}}(\boldsymbol\theta) \ = \ \displaystyle\sum_{(i, j) \in E} \theta_{ij}^{(1)} Z_{i} Z_{j} \ + \ \displaystyle\sum_{i} \theta_{i}^{(2)} Z_{i} \ + \ \displaystyle\sum_{i} X_{i},
$$

wobei E die Menge der Kanten im Interaktionsgraphen ist und Xi und Zi die Pauli-X und Pauli-Z auf dem i-ten Qubit.

In diesem Tutorium wählen wir die Zielparameter durch Stichproben aus einer gleichmäßigen Wahrscheinlichkeitsverteilung im Bereich von -2 bis 2, mit einer Genauigkeit von zwei Dezimalstellen.

```
target_weights = [0.56, 1.24, 1.67, -0.79]
target_bias = [-1.44, -1.43, 1.18, -0.93]
```

Theoretisch können diese Parameter jeden beliebigen Wert annehmen, vorausgesetzt, sie sind so klein, dass das QGRNN sie in einer vertretbaren Anzahl von Optimierungsschritten erreichen kann. In matrix\_params steht die erste Liste für die ZZ-Wechselwirkungsparameter und die zweite Liste für die Einzel-Qubit-Z

Parameter.

Schließlich verwenden wir diese Informationen, um die Matrixform der Ising-Modell-Hamiltonschen in der Berechnungsbasis zu erzeugen:

```
def create_hamiltonian_matrix(n_qubits, graph, weights, bias):

    full_matrix = np.zeros((2 ** n_qubits, 2 ** n_qubits))

    # Creates the interaction component of the Hamiltonian
    for i, edge in enumerate(graph.edges):
        interaction_term = 1
        for qubit in range(0, n_qubits):
            if qubit in edge:
                interaction_term = np.kron(interaction_term, qml.PauliZ.matrix)
            else:
                interaction_term = np.kron(interaction_term, np.identity(2))
        full_matrix += weights[i] * interaction_term

    # Creates the bias components of the matrix
    for i in range(0, n_qubits):
        z_term = x_term = 1
        for j in range(0, n_qubits):
            if j == i:
                z_term = np.kron(z_term, qml.PauliZ.matrix)
                x_term = np.kron(x_term, qml.PauliX.matrix)
            else:
                z_term = np.kron(z_term, np.identity(2))
                x_term = np.kron(x_term, np.identity(2))
        full_matrix += bias[i] * z_term + x_term

    return full_matrix


# Prints a visual representation of the Hamiltonian matrix
ham_matrix = create_hamiltonian_matrix(qubit_number, ising_graph, target_weights, target_bias)
plt.matshow(ham_matrix, cmap="hot")
plt.show()
```

![](<../../.gitbook/assets/grafik (10).png>)

## Quantum-Data vorbereiten:

Die Sammlung von Quantendaten, die für den Betrieb des QGRNN benötigt wird, besteht aus zwei Komponenten: (i) Kopien eines Niedrigenergiezustands und (ii) eine Sammlung von zeitlich entwickelten Zuständen, die jeweils einfach der zu verschiedenen Zeiten entwickelte Niedrigenergiezustand sind. Im Folgenden ist ein Niedrigenergiezustand des Ziel-Hamiltonian dargestellt:

```
low_energy_state = [
    (-0.054661080280306085 + 0.016713907320174026j),
    (0.12290003656489545 - 0.03758500591109822j),
    (0.3649337966440005 - 0.11158863596657455j),
    (-0.8205175732627094 + 0.25093231967092877j),
    (0.010369790825776609 - 0.0031706387262686003j),
    (-0.02331544978544721 + 0.007129899300113728j),
    (-0.06923183949694546 + 0.0211684344103713j),
    (0.15566094863283836 - 0.04760201916285508j),
    (0.014520590919500158 - 0.004441887836078486j),
    (-0.032648113364535575 + 0.009988590222879195j),
    (-0.09694382811137187 + 0.02965579457620536j),
    (0.21796861485652747 - 0.06668776658411019j),
    (-0.0027547112135013247 + 0.0008426289322652901j),
    (0.006193695872468649 - 0.0018948418969390599j),
    (0.018391279795405405 - 0.005625722994009138j),
    (-0.041350974715649635 + 0.012650711602265649j),
]
```

Dieser Zustand kann durch eine entkoppelte Version des [Variational Quantum Eigensolver Algorithmus (VQE) ](https://pennylane.ai/qml/demos/tutorial\_vqe\_qng.html)erreicht werden. Im Wesentlichen wählen wir einen VQE-Ansatz, so dass der Schaltkreis den exakten Grundzustand nicht erlernen kann, aber er kommt ihm ziemlich nahe. Eine andere Möglichkeit, zum gleichen Ergebnis zu kommen, besteht darin, VQE mit einem vernünftigen Ansatz durchzuführen, den Algorithmus aber zu beenden, bevor er zum Grundzustand konvergiert. Wenn wir den exakten Grundzustand |ψ0⟩

verwenden, wäre die Zeitabhängigkeit trivial und die Daten würden nicht genügend Informationen über die Hamilton-Parameter liefern.

Wir können überprüfen, ob es sich um einen energiearmen Zustand handelt, indem wir numerisch den niedrigsten Eigenwert des Hamiltonians ermitteln und ihn mit der Energieerwartung dieses energiearmen Zustands vergleichen:

```
res = np.vdot(low_energy_state, (ham_matrix @ low_energy_state))
energy_exp = np.real_if_close(res)
print(f"Energy Expectation: {energy_exp}")


ground_state_energy = np.real_if_close(min(np.linalg.eig(ham_matrix)[0]))
print(f"Ground State Energy: {ground_state_energy}")

```

Wir haben in der Tat einen Nicht-Grundzustand mit niedriger Energie gefunden, da die erwartete Energie etwas größer ist als die Energie des echten Grundzustands. Dies ist jedoch nur die Hälfte der Informationen, die wir benötigen. Wir benötigen auch eine Sammlung zeitlich entwickelter Zustände mit niedriger Energie. Die zeitliche Entwicklung des energiearmen Zustands ist recht einfach: Wir müssen lediglich den Ausgangszustand mit einer Zeitentwicklungseinheit multiplizieren. Diese Operation kann als benutzerdefiniertes Gatter in PennyLane definiert werden:

```
def state_evolve(hamiltonian, qubits, time):

    U = scipy.linalg.expm(-1j * hamiltonian * time)
    qml.QubitUnitary(U, wires=qubits)
```

Wir erzeugen zwar noch keine zeitlich veränderten Quantendaten, aber wir haben jetzt alle Teile, die für ihre Vorbereitung erforderlich sind.

## Traning vom Hamiltonian

With the quantum data defined, we are able to construct the QGRNN and learn the target Hamiltonian. Each of the exponentiated Hamiltonians in the QGRNN ansatz,

$$
\hat{H}^{j}_{\text{Ising}}(\boldsymbol\mu)
$$

sind die Terme ZZ, Z und X aus dem Ising-Hamiltonian. Dies ergibt:

```
def qgrnn_layer(weights, bias, qubits, graph, trotter_step):

    # Applies a layer of RZZ gates (based on a graph)
    for i, edge in enumerate(graph.edges):
        qml.MultiRZ(2 * weights[i] * trotter_step, wires=(edge[0], edge[1]))

    # Applies a layer of RZ gates
    for i, qubit in enumerate(qubits):
        qml.RZ(2 * bias[i] * trotter_step, wires=qubit)

    # Applies a layer of RX gates
    for qubit in qubits:
        qml.RX(2 * trotter_step, wires=qubit)
```

Wie bereits im ersten Abschnitt erwähnt, hat das QGRNN zwei Register. In einem Register wird ein Teil der Quantendaten |ψ(t)⟩vorbereitet wird und in der anderen haben wir $$U_{H}(\boldsymbol\mu, \ \Delta) |\psi_0\rangle$$|². Um diesen Wert zu berechnen, wird ein SWAP-Test zwischen den Registern durchgeführt:

```
def swap_test(control, register1, register2):

    qml.Hadamard(wires=control)
    for reg1_qubit, reg2_qubit in zip(register1, register2):
        qml.CSWAP(wires=(control, reg1_qubit, reg2_qubit))
    qml.Hadamard(wires=control)
```

Nach der Durchführung dieser Prozedur ist der von einer Messung der Schaltung zurückgegebene Wert ⟨Z⟩, bezogen auf das Kontroll-Qubit. Die Wahrscheinlichkeit, den Zustand |0⟩ in diesem Kontroll-Qubit zu messen, hängt sowohl von der Treue zwischen den Registern als auch von ⟨Z⟩ ab. Mit ein wenig Algebra finden wir also heraus, dass ⟨Z⟩

gleich der Wiedergabetreue ist.

Bevor wir das vollständige QGRNN und die Kostenfunktion erstellen, legen wir einige weitere feste Werte fest. Dazu gehört ein "geschätzter" Interaktionsgraph, den wir auf einen vollständigen Graphen festlegen. Diese Wahl ist durch die Tatsache motiviert, dass jeder Zielinteraktionsgraph ein Untergraph dieser anfänglichen Vermutung sein wird. Ein Teil der Idee hinter dem QGRNN ist, dass wir den Interaktionsgraphen nicht kennen und er gelernt werden muss. In diesem Fall wird der Graph automatisch gelernt, wenn die Zielparameter optimiert werden. Die μ Parameter, die Kanten entsprechen, die im Zielgraphen nicht vorhanden sind, werden einfach gegen 0 gesetzt.

```
# Defines some fixed values

reg1 = tuple(range(qubit_number))  # First qubit register
reg2 = tuple(range(qubit_number, 2 * qubit_number))  # Second qubit register

control = 2 * qubit_number  # Index of control qubit
trotter_step = 0.01  # Trotter step size

# Defines the interaction graph for the new qubit system

new_ising_graph = nx.complete_graph(reg2)

print(f"Edges: {new_ising_graph.edges}")
nx.draw(new_ising_graph)
```

![](<../../.gitbook/assets/grafik (8).png>)

Auf diese Weise implementieren wir die QGRNN-Schaltung für einen bestimmten Zeitwert:

```
def qgrnn(weights, bias, time=None):

    # Prepares the low energy state in the two registers
    qml.QubitStateVector(np.kron(low_energy_state, low_energy_state), wires=reg1 + reg2)

    # Evolves the first qubit register with the time-evolution circuit to
    # prepare a piece of quantum data
    state_evolve(ham_matrix, reg1, time)

    # Applies the QGRNN layers to the second qubit register
    depth = time / trotter_step  # P = t/Delta
    for _ in range(0, int(depth)):
        qgrnn_layer(weights, bias, reg2, new_ising_graph, trotter_step)

    # Applies the SWAP test between the registers
    swap_test(control, reg1, reg2)

    # Returns the results of the SWAP test
    return qml.expval(qml.PauliZ(control))
```

Wir haben die vollständige QGRNN-Schaltung, aber wir müssen noch eine Kostenfunktion definieren. Wir wissen, dass $$| \langle \psi(t) | U_{H}(\boldsymbol\mu, \ \Delta) |\psi_0\rangle |^2$$

where we use $$N$$

pieces of quantum data.

Bevor wir die Kostenfunktion erstellen, müssen wir noch einige feste Variablen definieren:

```
N = 15  # The number of pieces of quantum data that are used for each step
max_time = 0.1  # The maximum value of time that can be used for quantum data
```

Anschließend definieren wir die Kostenfunktion der negativen Wiedergabetreue:

```
rng = np.random.default_rng(seed=42)

def cost_function(weight_params, bias_params):

    # Randomly samples times at which the QGRNN runs
    times_sampled = rng.random(size=N) * max_time

    # Cycles through each of the sampled times and calculates the cost
    total_cost = 0
    for dt in times_sampled:
        result = qgrnn_qnode(weight_params, bias_params, time=dt)
        total_cost += -1 * result

    return total_cost / N
```

Als Nächstes bereiten wir uns auf die Optimierung vor.

```
# Defines the new device
qgrnn_dev = qml.device("default.qubit", wires=2 * qubit_number + 1)

# Defines the new QNode
qgrnn_qnode = qml.QNode(qgrnn, qgrnn_dev)

steps = 300

optimizer = qml.AdamOptimizer(stepsize=0.5)

weights = rng.random(size=len(new_ising_graph.edges), requires_grad=True) - 0.5
bias = rng.random(size=qubit_number, requires_grad=True) - 0.5

initial_weights = copy.copy(weights)
initial_bias = copy.copy(bias)
```

Jetzt muss nur noch die Optimierungsschleife ausgeführt werden.

```
for i in range(0, steps):
    (weights, bias), cost = optimizer.step_and_cost(cost_function, weights, bias)

    # Prints the value of the cost function
    if i % 5 == 0:
        print(f"Cost at Step {i}: {cost}")
        print(f"Weights at Step {i}: {weights}")
        print(f"Bias at Step {i}: {bias}")
        print("---------------------------------------------")
```

Mit den gelernten Parametern konstruieren wir eine visuelle Darstellung des Hamiltonian, dem sie entsprechen, und vergleichen sie mit dem Ziel-Hamiltonian und dem anfänglich vermuteten Hamiltonian:

```
new_ham_matrix = create_hamiltonian_matrix(
    qubit_number, nx.complete_graph(qubit_number), weights, bias
)

init_ham = create_hamiltonian_matrix(
    qubit_number, nx.complete_graph(qubit_number), initial_weights, initial_bias
)

fig, axes = plt.subplots(nrows=1, ncols=3, figsize=(6, 6))

axes[0].matshow(ham_matrix, vmin=-7, vmax=7, cmap="hot")
axes[0].set_title("Target", y=1.13)

axes[1].matshow(init_ham, vmin=-7, vmax=7, cmap="hot")
axes[1].set_title("Initial", y=1.13)

axes[2].matshow(new_ham_matrix, vmin=-7, vmax=7, cmap="hot")
axes[2].set_title("Learned", y=1.13)

plt.subplots_adjust(wspace=0.3, hspace=0.3)
plt.show()
```

![](<../../.gitbook/assets/grafik (4).png>)

Diese Bilder sehen sehr ähnlich aus, was darauf hindeutet, dass das QGRNN den Ziel-Hamiltonian gut gelernt hat.

Wir können uns auch die genauen Werte des Ziels und der gelernten Parameter ansehen. Der Zielinteraktionsgraph hat 4 Kanten, während der vollständige Graph 6 Kanten hat. Wenn das QGRNN also zur optimalen Lösung konvergiert, sollten die Gewichte, die den Kanten (1,3) und (2,0) im vollständigen Graphen entsprechen, auf 0 sinken, da dies anzeigt, dass sie keinen Effekt haben und im gelernten Hamiltonian nicht existieren.

```
# We first pick out the weights of edges (1, 3) and (2, 0)
# and then remove them from the list of target parameters

weights_noedge = []
weights_edge = []
for ii, edge in enumerate(new_ising_graph.edges):
    if (edge[0] - qubit_number, edge[1] - qubit_number) in ising_graph.edges:
        weights_edge.append(weights[ii])
    else:
        weights_noedge.append(weights[ii])
```

Dann drucken wir alle Gewichte aus:

```
print("Target parameters     Learned parameters")
print("Weights")
print("-" * 41)
for ii_target, ii_learned in zip(target_weights, weights_edge):
    print(f"{ii_target : <20}|{ii_learned : >20}")

print("\nBias")
print("-"*41)
for ii_target, ii_learned in zip(target_bias, bias):
    print(f"{ii_target : <20}|{ii_learned : >20}")

print(f"\nNon-Existing Edge Parameters: {[val.unwrap() for val in weights_noedge]}")
```

Die Gewichte der Kanten (1,3) und (2,0) sind sehr nahe an 0

was bedeutet, dass wir den Zyklusgraphen aus dem vollständigen Graphen gelernt haben. Darüber hinaus liegen die übrigen gelernten Gewichte ziemlich nahe an denen des Ziel-Hamiltonianers. Das QGRNN funktioniert also ordnungsgemäß und hat den Ising-Hamiltonschen mit einem hohen Grad an Genauigkeit gelernt!

Thanks a lot to Verdon, G., McCourt, T., Luzhnica, E., Singh, V., Leichenauer, S., & Hidary, J. (2019). Quantum Graph Neural Networks. arXiv preprint [arXiv:1909.12264](https://arxiv.org/abs/1909.12264).

and _Jack Ceroni & pennylane team for this awesome article_
