---
layout: post
title: "Post with Image Feature"
date: 2024-02-11
excerpt: "A ton of text to test readability with image feature."
tags: [sample post, readability, test, image, feature]
feature: http://i.imgur.com/Ds6S7lJ.png
comments: true
---

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

\documentclass{article}
\usepackage[left=1in, right=1in, top=1in, bottom=1.5in]{geometry}
\usepackage{amsmath} % 引入数学包
\begin{document}
	\begin{flushright}
		Lin Wenjuan
		
		wenjuan.23
		
		HW9
		
	\end{flushright}
	
\section*{Problem 1}

\begin{align*}
	\left\{
	\begin{array}{l}
		E[X]=\frac{a+b}{2}=1 \\
		Var(X)=\frac{(b-a)^2}{12}=3 
	\end{array}
	\right.
\end{align*}

So $a=-2, b=4$

So 
\begin{align*}
	f_X(x)=
	\left\{
	\begin{array}{l}
		\frac{1}{6}, -2\leq x \leq 4 \\
		\\
		0, otherwise 
	\end{array}
	\right.
\end{align*}

Because $Y=|X|$

\begin{align*}
	f_Y(u)=
	\left\{
	\begin{array}{l}
		\frac{1}{3}, 0\leq u \leq 2 \\
		\\
		\frac{1}{6}, 2< u \leq 4 \\
		\\
		0, otherwise 
	\end{array}
	\right.
\end{align*}

\section*{Problem 2}

\[f_X(u)=\frac{1}{\pi(1+u^2)}\]

\[F_X(u)=\int_{-\infty}^{u}\frac{1}{\pi(1+x^2)}dx=\frac{1}{\pi}(arctan(u)-\frac{\pi}{2})\]

Assume that q is a non-zero real number.

\[P\{Y \leq q\}=P\{\frac{1}{X} \leq q\}=1-P\{X < \frac{1}{q}\}=\frac{3}{2}-\frac{1}{\pi}arctan(\frac{1}{q})\]

So \[F_Y(q)=\frac{3}{2}-\frac{1}{\pi}arctan(\frac{1}{q})\]

So \[f_Y(q)=\frac{d}{dq}F_Y(q)=-\frac{1}{\pi}\cdot(\frac{1}{1+(\frac{1}{q})^2}\cdot\frac{-1}{q^2})=\frac{1}{\pi(1+q^2)}(q\neq0)\]


\section*{Problem 3}

\[F_X(x)=\int_{0}^{x} dx=x\]

Assume that q is a read number which is greater or equal to zero.

\[P\{Y\leq q\}=P\{g^{-1}(Y)\leq g^{-1}(q)\}=P\{X\leq g^{-1}(q)\}=F_X(g^{-1}(q))=g^{-1}(q)\]

Because

\[P\{Y\leq q\}=F_Y(q)=1-e^{-(\frac{q}{\alpha})^\beta}\]

So

\[g^{-1}(q)=1-e^{-(\frac{q}{\alpha})^\beta}\]

Therefore

\[g(x)=\alpha\cdot(-ln(1-x))^{\frac{1}{\beta}}\]


Check:

\begin{align*}
	F_Y(v)&=P\{Y\leq v\} \\ 
	&=P\{\alpha\cdot(-ln(1-X))^{\frac{1}{\beta}} \leq v\} \\
	&=P\{(-ln(1-X))\leq (\frac{v}{\alpha})^{\beta}\}\\
	&=P\{1-X\geq e^{-(\frac{v}{\alpha})^{\beta}}\} \\
	&=P\{X\leq 1-e^{-(\frac{v}{\alpha})^{\beta}}\} \\
	&=1-e^{-(\frac{v}{\alpha})^{\beta}} 
\end{align*}

Therefore, this indeed gives the desired distribution.

#problem 4

\subsection*{(a) Find the ML rule}


likelihood ratio: \[\Lambda(u)=\frac{f_1(u)}{f_0(u)}\]

For $u\in[\frac{-1}{2},0), f_0(u)=\frac{1}{4}, f_1(u)=0,\text{ choose } H_0$

\vspace{5pt}

For $u\in[0,\frac{3}{2}], f_0(u)=\frac{1}{4}, f_1(u)=\frac{1}{4}u,\Lambda(u)=u$

\vspace{5pt}

~~~~So when $u\in[0,1),\text{ choose } H_0;$

\vspace{5pt}

~~~~when $u\in[1,\frac{3}{2}],\text{ choose } H_1$

\vspace{5pt}

For $u\in(\frac{3}{2},2], f_0(u)=0, f_1(u)=\frac{1}{4}u,\text{ choose } H_1$

\vspace{5pt}

For $u\in(2,\frac{5}{2}), f_0(u)=0, f_1(u)=\frac{-1}{4}u+1,\text{ choose } H_1$

\vspace{5pt}

For $u\in[\frac{5}{2},4], f_0(u)=\frac{1}{4}, f_1(u)=\frac{-1}{4}u+1,\Lambda(u)=-u+4$

\vspace{5pt}

~~~~So when $u\in[\frac{5}{2},3],\text{ choose } H_1;$

\vspace{5pt}

~~~~when $u\in(3,4],\text{ choose } H_0$

\vspace{5pt}

For $u\in(4,\frac{9}{2}], f_0(u)=\frac{1}{4}, f_1(u)=0,\text{ choose } H_0$

\vspace{5pt}

Therefore, ML decision rule:

\vspace{5pt}

~~~~When $u\in[\frac{-1}{2},1)\bigcup(3,\frac{9}{2}],\text{ choose }H_0;$

\vspace{5pt}

~~~~When $u\in[1,3],\text{ choose }H_1$

\subsection*{(b) Find $p_{false~alarm}$, $p_{miss}$, and $p_e$ for the ML rule}

\[p_{false~alarm}=P\{declare~H_1~is~true~|~H_0\}=\int_{1}^{\frac{3}{2}}\frac{1}{4}dx+\int_{\frac{5}{2}}^{3}\frac{1}{4}dx=\frac{1}{2}\cdot\frac{1}{4}+\frac{1}{2}\cdot\frac{1}{4}=\frac{1}{4}\]

\[p_{miss}=P\{declare~H_0~is~true~|~H_1\}=\int_{0}^{1}\frac{1}{4}x\cdot dx+\int_{3}^{4}(\frac{-1}{4}x+1)\cdot dx=\frac{1}{8}\cdot 1^2+(-\frac{1}{8}\cdot 4^2+4)-(-\frac{1}{8}\cdot  3^2+3)=\frac{1}{4}\]


\[p_e=\pi_0\cdot p_{false~alarm}+\pi_1\cdot p_{miss}=\frac{1}{5}\cdot \frac{1}{4}+\frac{4}{5}\cdot \frac{1}{4}=\frac{1}{4}\]


\subsection*{(c) Find the MAP rule}

\[\tau= \frac{\pi_0}{\pi_1}=\frac{1}{4}\]

likelihood ratio: \[\Lambda(u)=\frac{f_1(u)}{f_0(u)}\]

For $u\in[\frac{-1}{2},0), f_0(u)=\frac{1}{4}, f_1(u)=0,\text{ choose } H_0$

\vspace{5pt}

For $u\in[0,\frac{3}{2}], f_0(u)=\frac{1}{4}, f_1(u)=\frac{1}{4}u,\Lambda(u)=u$

\vspace{5pt}

~~~~So when $u\in[0,\frac{1}{4}),\text{ choose } H_0;$

\vspace{5pt}

~~~~when $u\in[\frac{1}{4},\frac{3}{2}],\text{ choose } H_1$

\vspace{5pt}

For $u\in(\frac{3}{2},2], f_0(u)=0, f_1(u)=\frac{1}{4}u,\text{ choose } H_1$

\vspace{5pt}

For $u\in(2,\frac{5}{2}), f_0(u)=0, f_1(u)=\frac{-1}{4}u+1,\text{ choose } H_1$

\vspace{5pt}

For $u\in[\frac{5}{2},4], f_0(u)=\frac{1}{4}, f_1(u)=\frac{-1}{4}u+1,\Lambda(u)=-u+4$

\vspace{5pt}

~~~~So when $u\in[\frac{5}{2},\frac{15}{4}],\text{ choose } H_1;$

\vspace{5pt}

~~~~when $u\in(\frac{15}{4},4],\text{ choose } H_0$

\vspace{5pt}

For $u\in(4,\frac{9}{2}], f_0(u)=\frac{1}{4}, f_1(u)=0,\text{ choose } H_0$

\vspace{5pt}

Therefore, MAP decision rule:

\vspace{5pt}

~~~~When $u\in[\frac{-1}{2},\frac{1}{4})\bigcup(\frac{15}{4},\frac{9}{2}],\text{ choose }H_0;$

\vspace{5pt}

~~~~When $u\in[\frac{1}{4},\frac{15}{4}],\text{ choose }H_1$

\subsection*{(d) Find $p_{false~alarm}$, $p_{miss}$, and $p_e$ for the MAP rule}

\[p_{false~alarm}=P\{declare~H_1~is~true~|~H_0\}=\int_{\frac{1}{4}}^{\frac{3}{2}}\frac{1}{4}dx+\int_{\frac{5}{2}}^{\frac{15}{4}}\frac{1}{4}dx=\frac{5}{4}\cdot\frac{1}{4}+\frac{5}{4}\cdot\frac{1}{4}=\frac{5}{8}\]

\[p_{miss}=P\{declare~H_0~is~true~|~H_1\}=\int_{0}^{\frac{1}{4}}\frac{1}{4}x\cdot dx+\int_{\frac{15}{4}}^{4}(\frac{-1}{4}x+1)\cdot dx=\frac{1}{8}\cdot(\frac{1}{4})^2+(-\frac{1}{8}\cdot 4^2+4)-(-\frac{1}{8}\cdot (\frac{15}{4})^2+\frac{15}{4})=\frac{1}{64}\]


\[p_e=\pi_0\cdot p_{false~alarm}+\pi_1\cdot p_{miss}=\frac{1}{5}\cdot \frac{5}{8}+\frac{4}{5}\cdot \frac{1}{64}=\frac{11}{80}\]



\section*{Problem 5}

\subsection*{(a) average radius}

\[E[R]=\int_{0}^{1} x\cdot (2x) dx=\frac{2}{3}\cdot 1^3=\frac{2}{3}\]

\subsection*{(b) average volume}

\[E[\frac{4}{3}\pi R^3]=\int_{0}^{1} \frac{4}{3} \pi x^3\cdot (2 x) dx=\frac{8\pi}{15}\cdot 1^5=\frac{8}{15}\pi\]

\subsection*{(c) average surface area}

\[E[4\pi R^2]=\int_{0}^{1} 4 \pi x^2\cdot (2x) dx=2\pi\cdot 1^4=2\pi\]

\subsection*{(d)}


\begin{align*}
	average~sphere:
	\left\{
	\begin{array}{l}
		V=\frac{4}{3}\pi\cdot(\frac{2}{3})^3=\frac{32}{81}\pi < E[\frac{4}{3}\pi R^3]\\
		\\
		S=4\pi\cdot(\frac{2}{3})^2=\frac{16}{9}\pi < E[4\pi R^2] \\
	\end{array}
	\right.
\end{align*}

less than average volume and average surface area
\end{document}
