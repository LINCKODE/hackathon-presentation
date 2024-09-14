# Greetings
Hello everyone! Thanks for attending today's class on Qubic. My name is LINCKODE, you can call me Daniel and I am a back-end developer for Qubic. I will be your mentor for the day.
By the end of today's session, I hope to have helped you understand what Qubic is and how to interact with the Qubic Network using our Integration layer.

# So what is Qubic?
As you may already know, Qubic is a blockchain, but there are some specific characteristics that make it quite special and differentiate it from other blockchains.

Some of these characteristics include:
- UPoW (Useful Proof of Work): UPoW means that the computation power of the network is not spent solving complex cryptographic puzzles, instead it is used to perform useful task and calculations, such as AI training.
- Quorum based: Qubic aims to allow every Node that is part of the network to have it's say regarding everything on the network. Thus we achieve a decentralized and democratic network, where everyone can vote on how the network moves forward.

# The network

Qubic is made up of multiple nodes running the [Qubic Node](https://github.com/qubic/core) software. These nodes, known as **Computors**, perform various tasks such as executing **Smart Contracts** or **Transaction** processing. 
Communication between the nodes is achieved through a custom, packet based protocol.

Together, the nodes assemble a **Quorum**, where every node can vote on different **Proposals** related to the network. The aim is to create a decentralized and democratic network, where every node has an equal say.
In order for the network to create new **Ticks** (blocks), the Quorum needs the votes of at least 451 nodes, where the majority decides the state of the network.

Ticks are organized into **Epochs**, which last 7 days, starting and ending on every Wednesday at 12 PM UTC. 
During an epoch change, the tick and transaction history of the old epoch is discarded, with only the state of the network during the last epoch tick being saved to disk.

[[Getting started]]
