Chapter 1 : Introdutcion

1. What is AI?

- Standard model: AI has focused on the study and construction of agents that do the right thing.
  What counts as the right thing is defined by the objective that we provide to the agent.

- 2 methods: 1. Human-like intelligence: related to psychology, involving observations and hypotheses about actual human behavior and thought processes 2. Rationalist approach: combination of mathematics and engineering, and connects to statistics, control theory, and economics

  1.1 Acting humanly: The Turing test approach

The computer to pass this test, would need the following capabilities:

- natural language processing to communicate successfully in a human language;

- knowledge representation to store what it knows or hears;

- automated reasoning to answer questions and to draw new conclusions;

- machine learning to adapt to new circumstances and to detect and extrapolate patterns

To pass the total Turing test (physical simulation of a person), a robot
will need:

- computer vision and speech recognition to perceive the world;

- robotics to manipulate objects and move about

  1.2 Thinking humanly: The cognitive modeling approach

We can learn about human thought in three ways:

- introspection: trying to catch our own thoughts as they go by
- psychological experiments: observing a person in action
- brain imaging: observing the brain in action

  1.3 Thinking rationally: The “laws of thought” approach

- Syllogism: Socrates is a man and all men are mortal and concludes that Socrates is mortal

Logic as conventionally understood requires knowledge of the world that is certain (in reality, rarely achieved). We simply don’t know the rules of politics or warfare in the same way that we know the rules of chess or arithmetic. The theory of probability fills this gap, allowing rigorous reasoning with uncertain information.
In principle, it allows the construction of a comprehensive model of rational thought,
leading from raw perceptual information to an understanding of how the world works to
predictions about the future. What it does not do, is generate intelligent behavior. For that,
we need a theory of rational action. Rational thought, by itself, is not enough.

1.4 Acting rationally: The rational agent approach

An agent is just something that acts.
Of course, all computer programs do something,
but computer agents are expected to do more:
operate autonomously,
perceive their environment,
persist over a prolonged time period,
adapt to change, and create and pursue goals.

A rational agent: act to achieve the best outcome or, when there is uncertainty, the best expected outcome

The rational-agent approach to AI has two advantages over the other approaches.

First, it is more general than the “laws of thought” approach because correct inference is just one of
several possible mechanisms for achieving rationality.

Second, it is more amenable to scientific development. The standard of rationality is mathematically well defined and completely general. We can often work back from this specification to derive agent designs
that provably achieve it-something that is largely impossible if the goal is to imitate human
behavior or thought processes.

The problem of achieving agreement between our true preferences and the objective we put
into the machine is called the value alignment problem: the values or objectives put into the machine must be aligned with those of the human. If we are developing an AI system in
the lab or in a simulator—as has been the case for most of the field’s history—there is an
easy fix for an incorrectly specified objective: reset the system, fix the objective, and try
again. As the field progresses towards increasingly capable intelligent systems that are
deployed in the real world, this approach is no longer viable. A system deployed with an
incorrect objective will have negative consequences. Moreover, the more intelligent the
system, the more negative the consequences.

There is good reason, then, to think that the standard model is
inadequate. We don’t want machines that are intelligent in the sense of pursuing their
objectives; we want them to pursue our objectives. If we cannot transfer those objectives
perfectly to the machine, then we need a new formulation—one in which the machine is
pursuing our objectives, but is necessarily uncertain as to what they are. When a machine
knows that it doesn’t know the complete objective, it has an incentive to act cautiously, to
ask permission, to learn more about our preferences through observation, and to defer to
human control. Ultimately, we want agents that are provably beneficial to humans.
