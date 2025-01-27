---
author: Tom Slee
comments: false
date: 2006-10-09 11:55:51+00:00
excerpt: "\n\t\t\t\t\t\t"
layout: post
link: http://tomslee.net/2006/10/quantum_computi.html
slug: quantum_computi
title: "\n\t\t\t\tQuantum Computing: Gripes from a Quantum Fuddy-Duddy\t\t"
wordpress_id: 308
---


				Waterloo is an interesting place to live these days for an ex-quantum-mechanic, mainly because of all that techno-geek BlackBerry money that is being splashed around. When I bike to work I go past the Perimeter Institute in Theoretical Physics at the beginning of my ride, and then go within a stone's throw of the Institute for Quantum Computing at the end, both of which are making waves these days. All these brainy young things pushing the boundaries of what we know and don't know, it's fun to watch.

The main media event recently has been the publication of the book "The Trouble with Physics" by the Perimeter Insitute's Lee Smolin, which is a criticism of String Theory and its 30-year failure to prove itself as something more than a promising candidate for a theory of everything. Smolin's book has been widely reviewed, often in conjunction with Peter Woit's "Not Even Wrong" which argues much the same thing. The title "Not Even Wrong" was a devastating putdown coined by Enrico Fermi of another physicist's work - the implication being it was so mistaken that you couldn't even show why and how it was incorrect. My own work was in the relatively mundane work of molecules rather than cosmological elementary particles; that is, it was quantum, but on our side of the Heisenberg Uncertainty Principle, not the other side. Both books argue that String Theory has become so removed from experiment that it has ceased to be science, and has become prone to building elaborate edifices on an insufficiently sound physical basis.

While PI has made the biggest splash locally, the Institute for Quantum Computing is a rising star too. And Quantum Computing is something that I feel I can get more of a handle on than String Theory, so I've been reading a bit about it. And what I see either exposes me for a quantum fuddy-duddy or suggests that Quantum Computing (QC from here on) could do with listening to the critiques of Smolin and applying it to themselves.

So here is what's wrong with quantum computing from what I can see. (Disclaimer: these opinions are based on a number of popular articles, my attempts to follow Scott Aaronson's excellent weblog [Shtetl-Optimized](http://www.scottaaronson.com/blog/), and the bit I have read of Jozef Gruska's 1999 text "Quantum Computing", which I actually got out of the library last week. These opinions are worth exactly what you paid for them.)

Reading a QC book is an odd thing for a regular physics type. Where are the Hamiltonians? Few and far between, it seems ("Hamiltonian" is mentioned in only a literal handful of places -- five -- in Gruska). Everything is about the action of unitary operators on states. For anyone reading this who is not a physicist, here's what that means. In physics, when things interact, that interaction is described by a Hamiltonian. If you're trying to solve a problem, your first step is to construct a Hamiltonian operator that describes the interaction you are studying, and then solve the equations that come from that. Unitary operators, on the other hand, describe a change in a quantum system from one state to another, which may sound like the same thing but isn't. In regular computers, circuits consist of many gates that carry out elementary operations (AND, OR, and so on). If you had a quantum "gate" then a unitary operator describes the change from input to output (that's the
change in state), and ignores the way in which the system gets from the one end of the gate to the other. The Hamiltonian would describe the actual physical operation that happens as the light or electron or nuclear spin goes from the input to the output.

That still might not be very clear, so here's the end result: the theory of QC is built in a manner that has become deliberately divorced from the real world. The "implementation" or the actual building of a computer is consciously separated from the theory of the logic and algorithms that you would build on top of this computer. There is a division of labour between theory and experiment that is present right down to the way the theory is constructed, and that is a bit of a problem because it means that every single thing that the theorists say is conditional. All the
theorems they prove need a big asterisk next to them saying "as long as someone can make a computer". As a footnote Richard Feynman, who knew what he was doing, did some early explorations in Quantum Computing and did approach it by building Hamiltonians and putting together Schrodinger equations - just what you'd expect a physicist to do.

You can see why the discipline has gone in this manner. Regular old classical computing, after all, followed a similar path. It started off with mathematicians (von Neumann and Turing) who set out a logical architecture of computers and algorithms, and this work was followed (loosely speaking, and as best I understand) by the engineers once the transistor was invented. And it makes sense that those interested in exploring algorithms can do so without needing to know all about welding - this stuff is complicated enough as it is. But we should keep in mind that there is always the possibility that the success of regular computing will not be repeated. The proof of the pudding and all that.

The second thing that bothers me about QC is related to this division of labour. Everywhere you look they are talking about "entanglement" and all the things that go along with it: Bell's inequalities, EPR experiments and so on. In Gruska's book Everett (of the "many-worlds interpretation") is mentioned as many times as Hamiltonian. Again, for a quantum fuddy-duddy this raises red flags. The wierdness of the quantum world is seductive - enough that my 1st year lecturer (the late Peter Dawber) felt he had to warn us "this is interesting, but it's interpretation. My advice is learn how to calculate and solve problems, and don't get stuck in the philosophical quicksand". Good advice that has been repeated by many a lecturer, I'm sure. And yet here are these QC-ers diving headlong into entangled states, and spending more time on them than on things with actual Hamiltonians. Looking in Gruska's index again, entanglement merits 42 mentions. Perhaps this is mainly a rhetorical point, but I do think it is worth making because entanglement is built into the culture of quantum computing.

Entanglement is connected to what happens when you prepare a multi-particle quantum state and then let the particles become separated. So you get paragraphs like this:


Prepare a system with two particles, each of which can have two values of spin, and send them off in opposite directions. Then measure one of the particles to find its spin. This measurement then immediately fixes the spin of the other particle, even though it's a long way away. The state of the two particles is entangled.


But you could also write this paragraph this way.


Prepare a system with two particles, each of which can have two values of spin, and send them off in opposite directions. Then measure the state of the system by checking one particle. This measurement tells you the spin of both particles.


The difference is that in the second phrasing avoids mention of entanglement, and focuses on the fact that this is a single quantum system we are talking about here, and that however far apart the two particles end up being, they still have to comprise a single quantum system, and that means _no messing _from the classical world. The two paragraphs refer to the same operations and mathematics, but the second avoids extraneous weirdness.

The two most mature methods of actually preparing quantum computers are NMR spectroscopy and ion traps. Ion traps deal with fine control of isolated quantum systems (as required for "entanglement") and involves very exotic and incredibly precise experimental apparatus. This is what you would expect if you are dealing with single systems: the expense of dealing with them grows as the size of the separation grows. NMR deals with many systems ([coffee cups](http://www.media.mit.edu/physics/publications/press/print/97.04.inq.pdf#search=%22quantum%20computing%20coffee%20cup%22), for example - the link is to a PDF file) and uses the fancy techniques of pulsed magnetic resonance to give these systems a variety of kicks. It's recently been extended to 12 "qubits" (individual spins), which is the biggest quantum computer to date.

But here is the odd thing, this most successful technique is not based on the single systems that are needed for entanglement. In fact, these same multi-pulse NMR experiments have been carried out for some years and the word "entanglement" never raised its head so far as I know until the Quantum Computation people got interested. In NMR you are dealing with qubits that are not
spatially separated (they are nuclei on the same molecule) and you are not dealing with a single quantum system described by a single state vector (you are dealing with a thermodynamic ensemble of quantum systems described by a density matrix). Myself, I could never follow the theory of multi-pulse NMR, but I'm pretty sure there was no mention of many-world interpretations in it.

So QC should realise that the consequences of "entanglement" are limited to inherently exotic systems with which you are unlikely to be able to build a real computer. It's useful in PR material to highlight the weirdness of the quantum world, but when talking science you should follow Occam, who said "avoid talking weirdness whenever possible". For example, when QC people talk about "maximally entangled states" or "Bell states" they simply mean a state in which you've measured spin along one axis when you're going to measure spin along another axis later. This can be talked about without reference to Bell or entanglement.

This thing with entanglement shows up in all kinds of popular articles by the practitioners of WC. As one example, [here](http://qubit.damtp.cam.ac.uk/articles/intros/gmn/gmn.php) is a popular piece by some of the theorists (Steane and van Dam) who
have demonstrated that you can use entanglement to enhance communication - that you can exploit the entanglement of a quantum state together with regular messages among observers at different places to get more efficient communications. The article reads in a fun enough way (it's about participants at a game show who each carry their own little qubit into a separate cubicle and then pass messages). But it's not possible. You can't carry a qubit around because in order to exploit entanglement you have to have a single quantum system. This kind of writing comes from thinking about measurement according to the first way I wrote the paragraph above (measure the particle) as opposed to the second (measure the system).

Perhaps I'm being overly picky about this because it is, after all, just a popular article (although it works in some concepts you would need undergraduate physics to understand before the end). But I can imagine QCers saying, "well, it's possible in principle". But like a lot of "in principle" arguments I don't buy it. I think Daniel Dennett dealt with this kind of argument in his brilliant "[Consciousness Explained](http://en.wikipedia.org/wiki/Consciousness_Explained)" when discussing the idea of a "brain in a vat" (aka the Matrix) where philosophers argue that you could "in principle" recreate the sensations of the world by stimulating the right portions of the brain. Dennett basically calls their bluff and accuses them of not thinking through the magnitude of the problem, and takes some time to spell out just how hugely implausible it is. Now it's not a proof, but I think the same kind of thing applies to these popularizations of entanglement. You can "in principle" have widely separated parts of a single quantum state outside a hugely expensive laboratory only if you don't think too hard about what the endeavour entails. In a sense, we're back to the use of Unitary operators by the theorists so they don't
have to think about implementations.

Well, this has been more rambling than I expected, so here's a summary of what I see as the main points.



	
  * The split between abstract theory and physical implementation in the structure of quantum computing is a dangerous game. It means that everything that quantum computing theory says needs to be taken with a big pinch of salt until realistic quantum computers are demonstrated. The widespread use of the rhetoric of entanglement and other ideas that focus on the non-intuitive parts of quantum mechanics exacerbates the problem by pulling QC theory further away from actual implementations.

	
  * The fact that the biggest quantum computers to date are NMR based demonstrates how little entanglement adds to the actual theory of QC. And the fact that the best alternative is the inherently exotic approach of ion traps is disheartening.


I hope I'm wrong. There's a lot of smart people working on quantum computing who I'm sure have thought through these issues more than I have, and they look like in some ways they are making progress (see [here](http://en.wikipedia.org/wiki/Timeline_of_quantum_computing)). But here are two predictions that will show whether I'm right or wrong in a few years. One is that what constitutes a major advance will be redefined. The participants in a field are always enthusiastic about the major advances that are happening, but if we see major experimental advances that are phrased in terms like "enhance the understanding of what is necessary for quantum computation" rather than "actually compute something" then watch out. Second, the [goals](http://qist.lanl.gov/pdfs/rm_intro.pdf) (PDF)  set out by some people in the field will not be achieved.

Well, that's my Canadian Thansgiving ramble. Now I'm going to plant some tulips, which, with a bit of luck, will appear simultaneously, as if by magic, in a coherent fashion next spring.

**Update: **A [recent post](http://www.scottaaronson.com/blog/2006/10/mistake-of-week-x-works-on-paper-but.html) at Shtetl Optimized discusses a [paper](http://www.arxiv.org/abs/quant-ph/0610117) that has some of the same criticisms as my post here, except done properly: "[Is Fault-Tolerant Quantum Computation Really Possible?](http://www.arxiv.org/abs/quant-ph/0610117) by M. I. Dyakonov." Fuddy-duddies unite!		
