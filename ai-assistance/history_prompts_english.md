# Prompt and output history — English translation

> **Translation notice.** The original interaction was conducted partly in Italian. For public accessibility, the Italian prose has been translated into English in this file. Mathematical notation, citations, the attached TeX source, and long LaTeX blocks already written in English are preserved rather than rewritten. The original-language record in [`history_prompts.md`](history_prompts.md) is the authoritative archival version.

## Prompt 1 — English translation

Remember the previous chats as well.

I will provide you with my proof of a **quantitative version of Chiti's inequality**. I want you to study it carefully and verify whether the same structure can be adapted to obtain a **quantitative version of the Kohler--Jobin inequality**.

The idea is to keep the Chiti proof as unchanged as possible, while replacing its first quantitative block with the corresponding argument based on **modified torsional rigidity and Brasco's Kohler--Jobin rearrangement**.

In the Chiti argument, the first quantitative proposition provides the control needed to introduce the level

```latex
\bar t=u^*(|B_\lambda|),
```

where \(B_\lambda\) is the ball with the same first eigenvalue as \(\Omega\). One controls \(\bar t\) quantitatively in terms of the deficit and, since

```latex
|\{u>\bar t\}|=|B_\lambda|,
```

one uses the truncation \((u-\bar t)_+\) to show that the superlevel set \(U_{\bar t}\) has a small Faber--Krahn deficit.

For Kohler--Jobin I would like to reproduce precisely this structure, changing the first step.

Start from the ball \(B_T\) with the same torsional rigidity as \(\Omega\),

```latex
T(B_T)=T(\Omega),
```

and normalize the problem at fixed torsional rigidity. Let \(u\) be the first eigenfunction of \(\Omega\). Introduce the **modified torsional rigidity associated with \(u\)** and the ball \(B_r\) defined by

```latex
T(B_r)=T_{\mathrm{mod}}(\Omega;u).
```

The point is to use Brasco's result on the Kohler--Jobin rearrangement as the **analogue of the first quantitative proposition in the Chiti argument**: a small Kohler--Jobin deficit should translate into quantitative control of the level structure of the eigenfunction through the modified torsional rigidity.

At this point define

```latex
\boxed{\bar t=u^*(|B_r|),}
```

so that

```latex
|\{u>\bar t\}|=|B_r|.
```

I then want you to reconstruct the level-set argument carefully and determine what quantitative estimate on \(\bar t\) can actually be obtained in terms of the Kohler--Jobin deficit. Do not assume a particular power of the deficit in advance: derive it from the proof and keep track of any losses.

Once \(\bar t\) has been controlled in terms of the Kohler--Jobin deficit, verify whether the rest of the proof can proceed essentially as in the Chiti argument. Consider

```latex
U_{\bar t}=\{u>\bar t\},
\qquad
(u-\bar t)_+,
```

use the truncation to show that \(U_{\bar t}\) has a small Faber--Krahn deficit with respect to \(B_r\), and from this pass to quantitative stability.

In the final step, however, instead of the eigenfunction result used in the Chiti argument, I want to use the **Allen--Kriventsov--Neumayer resolvent result**, applied to \(U_{\bar t}\) and \(B_r\). Finally, complete the comparison by passing from the core \(U_{\bar t}\) to \(\Omega\), and from \(B_r\) to the ball \(B_T\) with the same torsional rigidity.

The scheme I want to verify is therefore

```latex
\boxed{
\begin{array}{c}
\text{Chiti: first quantitative proposition}
\\\downarrow\\\bar t=u^*(|B_\lambda|)
\\\downarrow\\
U_{\bar t}\text{ almost optimal for FK}
\\\downarrow\\\text{quantitative stability}
\end{array}
\qquad\longleftrightarrow\qquad\begin{array}{c}
\text{Brasco: modified torsion / KJ rearrangement}
\\\downarrow\\\bar t=u^*(|B_r|)
\\\downarrow\\
U_{\bar t}\text{ almost optimal for FK}
\\\downarrow\\\text{AKN for the resolvent}.
\end{array}}
```

Verify rigorously that this correspondence is correct, consulting directly the results of Brasco and Allen--Kriventsov--Neumayer. In particular, I want to understand **which quantitative control of the levels replaces the first proposition in the Chiti argument, which estimate for \(\bar t\) follows from it, and which final exponent emerges naturally from the entire chain**, without imposing it in advance.

Answer by writing a TeX file.


### Attached TeX source — preserved unchanged

```tex
\documentclass[a4paper,11pt]{article}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage{lmodern}
\usepackage[english]{babel}
\usepackage[top=2.7cm,bottom=2.7cm,left=2.8cm,right=2.8cm]{geometry}
\usepackage{microtype}
\usepackage{braket}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{amsthm, aliascnt}
\usepackage{mathtools}
\usepackage{mathrsfs}
\usepackage{xcolor}
\usepackage[hyphens]{url}
\usepackage{hyperref}
%\usepackage[hyphenbreaks]{breakurl}
%\usepackage{enumitem}
\usepackage{enumerate}
\usepackage{tikz}
\usepackage[maxbibnames=99]{biblatex}
\addbibresource{Chiti_quantitative_biblio.bib}
\usepackage{csquotes}
\usetikzlibrary{patterns}
\usepackage{esint}
\usepackage{mleftright}%to use mleft and mright which have better spacing instead of left and right
\usepackage{yhmath}

\DeclareMathOperator*{\argmax}{arg,max}
\DeclareMathOperator*{\argmin}{arg,min}

%\usepackage{refcheck}

\hypersetup{
colorlinks=true,
linkcolor={black},
citecolor={blue},
urlcolor={blue},
pdftitle={A quantitative version of Chiti's inequality},
breaklinks=true}

\renewcommand*{\figureautorefname}{Figure}

\setlength{\parindent}{1.25em}
\setlength{\parskip}{0pt}
\setlength{\jot}{4pt}
\setlength{\abovedisplayskip}{9pt plus 2pt minus 2pt}
\setlength{\belowdisplayskip}{9pt plus 2pt minus 2pt}
\setlength{\abovedisplayshortskip}{5pt plus 2pt}
\setlength{\belowdisplayshortskip}{6pt plus 2pt minus 2pt}
\allowdisplaybreaks[2]
\emergencystretch=2em
\raggedbottom

\theoremstyle{plain}
\newtheorem{teor}{Theorem}
\numberwithin{teor}{section}
\numberwithin{equation}{section}
\providecommand*{\teorautorefname}{Theorem}
%
%
\theoremstyle{definition}
\newaliascnt{defi}{teor}
\newtheorem{defi}[defi]{Definition}
\aliascntresetthe{defi}
\providecommand*{\defiautorefname}{Definition}
%
%
\theoremstyle{plain}
\newaliascnt{lemma}{teor}% alias counter "<newTh>"
\newtheorem{lemma}[lemma]{Lemma}
\aliascntresetthe{lemma}
\providecommand*{\lemmaautorefname}{Lemma} % name for \autoref
%
%
\theoremstyle{plain}
\newaliascnt{prop}{teor}% alias counter "<newTh>"
\newtheorem{prop}[prop]{Proposition}
\aliascntresetthe{prop}
\providecommand*{\propautorefname}{Proposition} % name for \autoref
%
%
\theoremstyle{plain}
\newaliascnt{conjecture}{teor}% alias counter "<newTh>"
\newtheorem{conjecture}[conjecture]{Conjecture}
\aliascntresetthe{conjecture}
\providecommand*{\conjectureautorefname}{Conjecture} % name for \autoref
%
%
\theoremstyle{plain}
\newaliascnt{cor}{teor}% alias counter "<newTh>"
\newtheorem{cor}[cor]{Corollary}
\aliascntresetthe{cor}
\providecommand*{\corautorefname}{Corollary} % name for \autoref
%
%
\theoremstyle{definition}
\newaliascnt{ex}{teor}% alias counter "<newTh>"
\newtheorem{ex}[ex]{Example}
\aliascntresetthe{ex}
\providecommand*{\exautorefname}{Example} % name for \autoref
%
%
\theoremstyle{definition}
\newaliascnt{oss}{teor}% alias counter "<newTh>"
\newtheorem{oss}[oss]{Remark}
\aliascntresetthe{oss}
\providecommand*{\ossautorefname}{Remark} % name for \autoref
%
\theoremstyle{plain}
\newtheorem{open}{Open problem}
%\numberwithin{teor}{section}
%\numberwithin{equation}{section}
%
\newcommand{\Hlabel}[1]{%
\hypertarget{H#1}{}% crea l'anchor invisibile
\textnormal{\textcolor{magenta}{{H#1}}}%
}

% comando per citare nel testo
\newcommand{\Href}[1]{\hyperlink{#1}{\textnormal{\textcolor{magenta}{{#1}}}}}

\newcommand{\abs}[1]{{\left|#1\right|}}
\DeclarePairedDelimiter{\norma}{\lVert}{\rVert}
\DeclareMathOperator{\sbv}{SBV}
\DeclareMathOperator{\bv}{BV}
\DeclareMathOperator{\tr}{tr}
\DeclareMathOperator{\diam}{diam}
\DeclareMathOperator{\ric}{Ric}
\DeclareMathOperator{\spn}{span}
\DeclareMathOperator{\rhs}{rhs}
\newcommand{\marcomm}[1]{\marginpar{\begin{flushright}#1\end{flushright}}}% Serve per mettere a margine l'elenco dei passi di una dimostrazione
\newcommand{\R}{\mathbb{R}}
\newcommand{\sbvv}{\sbv^{\dfrac{1}{2}}(\R^n)}
\newcommand{\N}{\mathbb{N}}
\newcommand{\Ln}{\mathcal{L}^n}
\newcommand{\Hn}{\mathcal{H}^{n-1}}
\newcommand{\Hnn}{\mathcal{H}^{n-2}}
\newcommand{\hdu}{\widehat{\dot{u_t}}}
\newcommand{\B}{\mathbf{B}}
\newcommand{\dint}{\displaystyle\int}
\newcommand{\Om}{\Omega}
\newcommand{\la}{\lambda}
\newcommand{\eps}{\varepsilon}
\newcommand{\ssubset}{\subset\joinrel\subset}
\DeclareMathOperator{\divv}{div}
\DeclareMathOperator{\Id}{Id}
\DeclareMathOperator{\loc}{loc}
\DeclareMathOperator{\supp}{supp}
\DeclareMathOperator{\dist}{dist}
\DeclareMathOperator{\sgn}{sgn}
\DeclareMathOperator*{\esssup}{ess,sup}
\DeclareMathOperator{\Tr}{Tr}
\newcommand{\teal}[1]{{\color{teal} #1}}
\newcommand{\red}[1]{{\color{red} #1}}
% ----- IC -----
\newcommand{\IClabel}{%
\label{IC}%
\textnormal{\textbf{(IC$_{H^s,X}$)}}%
}

\newcommand{\ICref}{%
\textnormal{\textbf{(\hyperref[IC]{\textcolor{magenta}{IC$_{H^s,X}$}})}}%
}

% ----- Cs -----
\newcommand{\Cslabel}{%
\label{Cs}%
\textnormal{\textbf{(C$_{H^s}$)}}%
}

\newcommand{\Csref}{%
\textnormal{\textbf{(\hyperref[Cs]{\textcolor{magenta}{C$_{H^s}$}})}}%
}







\title{\bfseries A quantitative version of Chiti's inequality}
\author{}
\date{}

\begin{document}
\maketitle

\begin{abstract}
We prove a quantitative version of Chiti's reverse H"older inequality. For every $p>q>1$, its deficit controls, up to translations, the $L^q$-distance between the $L^q$-normalized first Dirichlet eigenfunction of a domain and that of the ball having the same first eigenvalue. In the range $1<q\leq2$ we also obtain a quantitative $W^{1,q}$ estimate. No upper bound on the measure of the domain is required.
\end{abstract}

\section{Introduction}

Symmetrization techniques provide a classical way of comparing solutions of partial differential equations on a general domain with radial solutions on a ball. In spectral problems, the Faber--Krahn inequality identifies balls as the minimizers of the first Dirichlet eigenvalue among sets with prescribed measure. A complementary point of view consists in fixing the first eigenvalue and comparing the concentration of the corresponding positive eigenfunctions. This is the setting of Chiti's reverse H"older inequality \cite{Chiti82RH,Chiti82Iso}.

Let $\Om\subset\R^n$, $n\geq2$, be a bounded, open and connected set. We denote by $\lambda=\lambda(\Om)$ its principal Dirichlet eigenvalue, defined by
[
\lambda(\Om)
:=
\min_{v\in H_0^1(\Om)\setminus{0}}
\frac{\displaystyle\int_{\Om}\abs{\nabla v}^2,dx}
{\displaystyle\int_{\Om}v^2,dx}.
]
A minimizer $u\in H_0^1(\Om)$ is called a principal Dirichlet eigenfunction of $\Om$. Equivalently, $u$ is a nontrivial weak solution of
[
\begin{cases}
-\Delta u=\lambda u & \text{in }\Om,\
u=0 & \text{on }\partial\Om.
\end{cases}
]
The eigenfunction $u$ can be chosen positive in $\Om$ and is unique up to multiplication by a constant. We denote by $B_\lambda$ the ball centred at the origin such that
[
\lambda(B_\lambda)=\lambda(\Om)=\lambda,
]
and we let $z$ be a positive principal Dirichlet eigenfunction of $B_\lambda$.

\norma{u}_{L^p(\Om)}^p.
\end{equation}

The purpose of this paper is to understand whether a small deficit forces the eigenfunction $u$ to be close to the radial model $z$. There are two natural difficulties. First, the two functions are defined on different domains and the problem is invariant under translations. Secondly, fixing $\lambda(\Om)$ does not provide an upper bound for $\abs{\Om}$: a domain may contain a large region on which its first eigenfunction is very small. The key observation is that the $L^q$ normalization transfers the entire $L^q$-mass of this tail to the fixed interval corresponding to $B_\lambda$. This makes it possible to obtain a global $L^q$ estimate without imposing any a priori bound on $\abs{\Om}$ and for every $q>1$.

We denote by $u^$ and $z^$ the decreasing rearrangements of $u$ and $z$, respectively, by $\Om^\sharp$ the ball centred at the origin such that $\abs{\Om^\sharp}=\abs{\Om}$, and by $u^\sharp$ the Schwarz rearrangement of $u$. We set
[
\theta:=\min\left{\frac13,\frac{1}{p+1}\right},
\qquad
b:=\abs{B_\lambda},
]
and introduce the distinguished level and superlevel set
[
\bar t:=u^*(b),
\qquad
U_{\bar t}:={x\in\Om(x)>\bar t}.
]
By construction, $\abs{U_{\bar t}}=\abs{B_\lambda}$. More precisely, our main result can be stated as follows.

\norma{u}{L^p(\Om)}^p,
\qquad
\theta:=\min\left{\frac13,\frac{1}{p+1}\right},
\qquad
\sigma:=\theta\min\left{1,\frac q2\right}.
]
Then there exist two positive constants $\delta_0$ and $C$, depending only on $n$, $\lambda$, $p$ and $q$, such that, if $\delta\leq\delta_0$, there exists $x_0\in\R^n$ for which
\begin{equation}\label{eq: main eigenfunction stability}
\norma{u-z(,\cdot-x_0)}{L^q(\R^n)}^q
\leq
C\delta^\sigma.
\end{equation}
Equivalently,
[
\norma{u-z(,\cdot-x_0)}_{L^q(\R^n)}
\leq
C\delta^{\frac{\theta}{\max{2,q}}}.
]
Here and in what follows, the eigenfunctions are extended by zero outside their domains.
\end{teor}

In the subquadratic range the conclusion can be strengthened to the Sobolev
norm. Notice that the exponent in the following statement is independent of
$q$.

\begin{teor}\label{teor: W1q stability}
Under the assumptions of \autoref{teor: main}, suppose in addition that
$1<q\leq2$. Then there exist two positive constants $\delta_0$ and $C$,
depending only on $n$, $\lambda$, $p$ and $q$, such that, if
$\delta\leq\delta_0$, there exists $x_0\in\R^n$ for which
\begin{equation}\label{eq: W1q eigenfunction stability}
\norma{u-z(,\cdot-x_0)}{W^{1,q}(\R^n)}^q
\leq
C\delta^{q\theta/6}.
\end{equation}
Equivalently,
[
\norma{u-z(,\cdot-x_0)}{W^{1,q}(\R^n)}
\leq
C\delta^{\theta/6}.
]
\end{teor}

The restriction $q\leq2$ in \autoref{teor: W1q stability} is structural for
the present class of domains. For an arbitrary bounded open set a principal
eigenfunction is a priori only in $H_0^1$, and no uniform $W^{1,q}$ regularity
with $q>2$ is available. In particular, the $L^\infty$ interpolation used in
the proof of \autoref{teor: main} cannot be applied to the gradients without
additional uniform regularity assumptions on the domains.

The constants in \autoref{teor: main} are uniform among all bounded, open and connected sets having principal eigenvalue $\lambda$; in particular, they do not depend on $\abs{\Om}$. The two regimes in the exponent $\sigma$ arise only when the $L^2$ eigenfunction stability for the Faber--Krahn inequality is converted into an $L^q$ estimate on sets of fixed measure: H"older's inequality is used for $q\leq2$, while interpolation with a uniform $L^\infty$ bound is used for $q\geq2$.

As a direct consequence of \autoref{teor: main} and of the estimate between the decreasing rearrangements, we also obtain that $u$ is quantitatively close to a translate of its Schwarz rearrangement.

\norma{u}{L^p(\Om)}^p,
\qquad
\theta:=\min\left{\frac13,\frac{1}{p+1}\right},
\qquad
\sigma:=\theta\min\left{1,\frac q2\right}.
]
Then there exist two positive constants $\delta_0$ and $C$, depending only on $n$, $\lambda$, $p$ and $q$, such that, if $\delta\leq\delta_0$, then
\begin{equation}\label{eq: Lq almost symmetry}
\inf{x_0\in\R^n}
\norma{u-u^\sharp(,\cdot-x_0)}_{L^q(\R^n)}^q
\leq
C\delta^\sigma.
\end{equation}
Both functions are extended by zero outside their domains.
\end{cor}

Let us briefly describe the proof. The first step is a weighted estimate for $z^-u^$, obtained by combining an elementary inequality between the powers $p$ and $q$ with the single-crossing property in Chiti's comparison theorem. We then exploit the $L^q$ normalization to control the tail of $u^$ independently of $\abs{\Om}$ and deduce a global $L^q$ estimate for the rearrangements. The boundary behaviour of $z^$ yields a bound for $\bar t$, and the truncation $(u-\bar t)+$ shows that $U{\bar t}$ is almost optimal in the Faber--Krahn inequality. The quantitative $L^2$ eigenfunction stability of Allen, Kriventsov and Neumayer \cite{AKN25} compares the first eigenfunction of $U_{\bar t}$ with a translate of $z$. Since both comparison domains have fixed measure and their normalized eigenfunctions satisfy uniform $L^\infty$ bounds, this estimate converts into an $L^q$ estimate for every $q>1$. Finally, a spectral-gap argument on $U_{\bar t}$ compares the truncation of $u$ with that eigenfunction, while the global $L^q$ tail estimate compares $u$ with its truncation. For the Sobolev estimate we combine the P'olya--Szeg\H{o} deficit with an integration-by-parts argument on $B_\lambda$. The gradient of the low-level tail is estimated without using $\abs{\Om}$ by testing the eigenvalue equation with a power of $\min{u,\bar t}$.

The paper is organized as follows. In Section~2 we recall the rearrangement notation and the comparison tools used throughout the paper. Section~3 contains the quantitative estimates for the Chiti deficit, the passage from the $L^2$ Faber--Krahn stability theorem to $L^q$, and the proof of the main theorem. Section~4 proves the $W^{1,q}$ estimate for $1<q\leq2$.

\section{Preliminaries}

For a non-negative measurable function $f$ on a set of finite measure, we denote by
[
\mu_f(t):=\abs{{x(x)>t}}
]
its distribution function and by $f^$ its decreasing rearrangement. The Schwarz rearrangement is the radial non-increasing function defined by
[
f^\sharp(x):=f^\bigl(\omega_n\abs{x}^n\bigr),
]
where $\omega_n$ denotes the measure of the unit ball of $\R^n$. Equimeasurability gives
[
\norma{f}{L^r}=\norma{f^*}{L^r}=\norma{f^\sharp}_{L^r}
\qquad
\text{for every }r\in[1,+\infty].
]

By the Faber--Krahn inequality, $b=\abs{B_\lambda}\leq\abs{\Om}$. Accordingly, throughout the paper we extend $z^$ by zero on $(b,\abs{\Om})$. Under the normalization
[
\norma{u}{L^q(\Om)}=\norma{z}{L^q(B_\lambda)},
]
Chiti's comparison theorem gives the single-crossing property of $u^$ and $z^$ \cite{Chiti82RH,Chiti82Iso}. In particular, the function
[
F(s):=\int_0^s\left((z^)^q-(u^*)^q\right),dt
]
satisfies
[
F(s)\geq0
\qquad
\text{for every }s\in[0,\abs{\Om}],
\qquad
F(0)=F(\abs{\Om})=0.
]
We shall also use Chiti's $L^\infty$ comparison,
[
\norma{u}{L^\infty(\Om)}
\leq
\norma{z}{L^\infty(B_\lambda)},
]
as well as domain monotonicity for the first Dirichlet eigenvalue and the Krahn--Szeg\H{o} inequality for the second one. Finally, the quantitative Faber--Krahn inequality and its eigenfunction version will be used in the form recalled in \autoref{oss: quantitative FK eigenfunctions}; see also \cite{BDPV15,AKN25}.

\section{Estimates for the Chiti deficit}

\subsection{A weighted estimate for the rearrangements}

\begin{lemma}
Let $a,b\geq0$ and $p>q>1$. Then there exists a constant $c=c(p,q)$ such that
\begin{equation}\label{dis a b p e q}
a^p-b^p\geq \dfrac{p}{q}b^{p-q}(a^q-b^q)+c(a-b)^2 (a+b)^{p-2}
\end{equation}
\end{lemma}
\begin{proof}
If $b=0$ the inequality is trivially true with $c=1$. Consider the case $b\not=0$ and let $t=\frac{a}{b}$, then
[a^p-b^p-\dfrac{p}{q}b^{p-q}(a^q-b^q)=b^p\left[t^p-1-\dfrac{p}{q}(t^q-1)\right],]
and
[(a-b)^2 (a+b)^{p-2}=b^p(t-1)^2(t+1)^{p-2}.]
Thus, it is sufficient to prove that the function $G:[0,+\infty)\to \mathbb R$ defined by
[
G(t)=\frac{t^p-1-\frac{p}{q}(t^q-1)}
{(t-1)^2(t+1)^{p-2}}
]
has a positive minimum. Indeed, the numerator is non-negative and vanishes only at $t=1$. Moreover, both the numerator and its first derivative vanish at $t=1$, whereas its second derivative at $t=1$ is equal to $p(p-q)>0$. Hence, $G$ admits a positive continuous extension at $t=1$. Finally,
[
\lim_{t\to+\infty}G(t)=1.
]
Therefore, by continuity, $G$ has a positive minimum on $[0,+\infty)$.

\end{proof}

\norma{u}{L^p(\Om)}^p.
]
Then there exists a positive constant $c=c(n,\lambda,p,q)$ such that
\begin{equation}\label{eq: weighted L2 rearrangements}
\delta
\geq
c\int_0^{\abs{\Om}}
(z^-u^)^2(z^+u^)^{p-2},dt.
\end{equation}
In particular, if $p\leq2$, then
\begin{equation}\label{eq: delta geq norma riarrangiamenti}
\delta
\geq
c\norma{z^-u^}{L^2(0,\abs{\Om})}^2,
\end{equation}
whereas, if $p>2$, then
\begin{equation}\label{eq: delta geq norma riarrangiamenti p geq 2}
\delta
\geq
c,\bar t^{p-2}
\norma{z^-u^}{L^2(0,\abs{B\lambda})}^2.
\end{equation}
\end{prop}

\int_0^{\abs{\Om}}
\left((z^)^p-(u^)^p\right),dt.
]
Therefore, by \eqref{dis a b p e q},
[
\begin{aligned}
\delta
&\geq
c\int_0^{\abs{\Om}}
(z^-u^)^2(z^+u^)^{p-2},dt
\
&\quad+
\frac{p}{q}
\int_0^{\abs{\Om}}
(u^)^{p-q}
\left((z^)^q-(u^)^q\right),dt.
\end{aligned}
]
Set
[
F(s)
:=
\int_0^s
\left((z^(t))^q-(u^(t))^q\right),dt,
\qquad
s\in[0,\abs{\Om}].
]
The normalization of $u$ and $z$ gives
[
F(0)=F(\abs{\Om})=0,
]
and Chiti's comparison theorem yields
[
F(s)\geq0
\qquad
\text{for every }s\in[0,\abs{\Om}].
]
Moreover, the function $h:=(u^)^{p-q}$ is non-increasing. Hence, integrating by parts in the Riemann--Stieltjes sense, we obtain
[
\begin{aligned}
\int_0^{\abs{\Om}}
(u^*)^{p-q}F',dt
&=
\int_{[0,\abs{\Om}]} h,dF
\
&=
-\int_{[0,\abs{\Om}]}F,dh
\geq0.
\end{aligned}
]
This proves \eqref{eq: weighted L2 rearrangements}.

\norma{z}{L^\infty(B\lambda)}
\qquad
\text{for every }t\in[0,\abs{\Om}],
]
and clearly $z^(t)\leq z^(0)$. Since $p-2\leq0$, it follows that
[
(z^+u^)^{p-2}
\geq
\left(2\norma{z}{L^\infty(B\lambda)}\right)^{p-2}.
]
Estimate \eqref{eq: delta geq norma riarrangiamenti} now follows from \eqref{eq: weighted L2 rearrangements}.

\bar t.
]
Consequently,
[
(z^(t)+u^(t))^{p-2}
\geq
\bar t^{p-2}.
]
Restricting the integral in \eqref{eq: weighted L2 rearrangements} to $(0,\abs{B_\lambda})$ gives \eqref{eq: delta geq norma riarrangiamenti p geq 2}.
\end{proof}

\norma{u}{L^p(\Om)}^p,
\qquad
\beta:=\min\left{\frac12,\frac{q}{p}\right}.
]
Then there exists a positive constant $C=C(n,\lambda,p,q)$ such that, if $\delta\leq1$, then
\begin{equation}\label{eq: Lq tail}
\int_b^{\abs{\Om}}(u^)^q,ds
\leq
C\delta^\beta,
\end{equation}
and
\begin{equation}\label{eq: Lq rearrangements}
\norma{z^-u^*}{L^q(0,\abs{\Om})}^q
\leq
C\delta^\beta.
\end{equation}
\end{prop}

\int_0^b\left((z^)^q-(u^)^q\right),ds.
\end{equation}
Since
[
\abs{a^q-b^q}
\leq
q\abs{a-b}(a+b)^{q-1}
\qquad
\text{for every }a,b\geq0,
]
we obtain
\begin{equation}\label{eq: tail preliminary}
\int_b^{\abs{\Om}}(u^*)^q,ds
\leq
q\int_0^b D S^{q-1},ds.
\end{equation}

W^{\frac12}S^{q-\frac p2}.
]
Since $q-p/2\geq0$, H"older's inequality, the bound $S\leq2M$ and \eqref{eq: weighted L2 rearrangements} yield
[
\int_0^b D S^{q-1},ds
\leq
C\left(\int_0^b W,ds\right)^{\frac12}
\leq
C\delta^{\frac12}.
]

W^{\frac qp}
\left(\frac{D}{S}\right)^{1-\frac{2q}{p}}
\leq
W^{\frac qp}.
]
Thus, again by H"older's inequality and \eqref{eq: weighted L2 rearrangements},
[
\int_0^b D S^{q-1},ds
\leq
b^{1-\frac qp}
\left(\int_0^b W,ds\right)^{\frac qp}
\leq
C\delta^{\frac qp}.
]
Estimate \eqref{eq: Lq tail} follows from \eqref{eq: tail preliminary}.

W^{q/p}
\left(\frac DS\right)^{q(1-2/p)}
\leq W^{q/p}
\qquad\text{on }{S>0}.
]
Hence
[
\int_0^bD^q,ds
\leq
b^{1-\frac qp}
\left(\int_0^bW,ds\right)^{q/p}
\leq
C\delta^{q/p}.
]
In both cases,
[
\int_0^bD^q,ds\leq C\delta^\beta.
]
Since $z^*=0$ on $(b,\abs{\Om})$, adding \eqref{eq: Lq tail} proves \eqref{eq: Lq rearrangements}.
\end{proof}

\subsection{The distinguished level and its superlevel set}

\norma{u}{L^p(\Om)}^p,
\qquad
\theta:=\min\left{\frac13,\frac{1}{p+1}\right}.
]
Then there exists a positive constant $k=k(n,\lambda,q)$ such that
\begin{equation}\label{eq: stima L2 t bar}
\norma{z^-u^}{L^2(0,b)}^2
\geq
k,\bar t^3.
\end{equation}
Consequently, there exists a positive constant $C=C(n,\lambda,p,q)$ such that
\begin{equation}\label{eq: t bar delta theta}
\bar t
\leq
C\delta^\theta.
\end{equation}
\end{prop}

\begin{proof}
Since $z$ is the positive principal eigenfunction of the ball, $z^$ is positive and decreasing in $[0,b)$ and satisfies
[
z^(b)=0.
]
Moreover, the regularity of $z$ up to the boundary implies that
[
\sup_{s\in[0,b)}
\frac{z^(s)}{b-s}
<+\infty.
]
Therefore, there exists a constant
[
K=K(n,\lambda,q)>0
]
such that
\begin{equation}\label{eq: linear bound z star boundary}
z^(s)
\leq
K(b-s)
\qquad
\text{for every }s\in[0,b].
\end{equation}
Up to enlarging $K$, we may also assume that
[
K\geq\frac{1}{2b^{1+\frac1q}}.
]

b\bigl(u^(b)\bigr)^q
\leq
\int_0^b(u^)^q,ds
\leq1.
]
It follows that
[
\bar t
\leq
b^{-\frac1q}
\leq
2Kb.
]
We therefore define
[
h:=\frac{\bar t}{2K},
]
which satisfies $0<h\leq b$.

\frac{1}{8K}\bar t^3,
\end{split}
]
which proves \eqref{eq: stima L2 t bar} with $k=(8K)^{-1}$.

If $p\leq2$, combining \eqref{eq: delta geq norma riarrangiamenti} and \eqref{eq: stima L2 t bar} yields
[
\delta
\geq
c\norma{z^-u^}{L^2(0,b)}^2
\geq
ck\bar t^3.
]
If $p>2$, combining \eqref{eq: delta geq norma riarrangiamenti p geq 2} and \eqref{eq: stima L2 t bar} gives
[
\delta
\geq
c\bar t^{p-2}
\norma{z^-u^}{L^2(0,b)}^2
\geq
ck\bar t^{p+1}.
]
These two estimates give \eqref{eq: t bar delta theta}.
\end{proof}

\begin{lemma}\label{lemma: stime ausiliarie}
Under the assumptions of \autoref{teor: main} there exist $\delta_1$ and $C$, depending only on $n$, $\lambda$, $p$ and $q$, such that, if $\delta\leq\delta_1$, then
\begin{equation}\label{eq: Lq truncation error}
\norma{u-(u-\bar t)+}{L^q(\Om)}^q
\leq C\delta^\theta,
\end{equation}
\begin{equation}\label{eq: truncation Lq lower bound}
\norma{(u-\bar t)+}{L^q(U_{\bar t})}\geq\frac12,
\end{equation}
\begin{equation}\label{eq: truncation L2 lower bound}
\norma{(u-\bar t)+}{L^2(U_{\bar t})}\geq c.
\end{equation}
\end{lemma}

b\bar t^q
+
\int_b^{\abs{\Om}}(u^*)^q,ds.
]
By \eqref{eq: t bar delta theta} and \eqref{eq: Lq tail},
[
\norma{u-v_{\bar t}}{L^q(\Om)}^q
\leq
C\delta^{q\theta}+C\delta^\beta
\leq C\delta^\theta.
]
Here we used $q>1$, $\delta\leq1$, and $\beta\geq\theta$. The reverse triangle inequality now yields
[
\norma{v{\bar t}}{L^q(U{\bar t})}
\geq
1-C\delta^{\theta/q}
\geq\frac12
]
for $\delta$ sufficiently small.

It remains to obtain a lower bound in $L^2$. If $q\leq2$, H"older's inequality on the set $U_{\bar t}$ of measure $b$ gives
[
\norma{v_{\bar t}}{L^2(U{\bar t})}
\geq
b^{\frac12-\frac1q}
\norma{v_{\bar t}}{L^q(U{\bar t})}
\geq c.
]
If $q>2$, Chiti's $L^\infty$ comparison gives $v_{\bar t}\leq u\leq M:=\norma{z}{L^\infty(B\lambda)}$, and therefore
[
\norma{v_{\bar t}}{L^2(U{\bar t})}^2
\geq
M^{2-q}\norma{v_{\bar t}}{L^q(U{\bar t})}^q
\geq c.
]
This proves all the assertions.
\end{proof}



\begin{cor}\label{cor: differenza autovalori}
Let the assumptions and the notation of \autoref{teor: main} hold. Then there exist constants $\delta_2>0$ and $C>0$, depending only on the parameters in \autoref{teor: main}, such that, if $\delta\leq\delta_2$, then
\begin{equation}\label{eq: differenza autovalori}
0
\leq
\lambda(U_{\bar t})-\lambda(\Om)
\leq
C\bar t
\leq
C\delta^\theta.
\end{equation}
\end{cor}

\begin{proof}
Set
[
v_{\bar t}:=(u-\bar t)+.
]
Since $v{\bar t}\in H_0^1(U_{\bar t})$, it is an admissible competitor in the Rayleigh characterization of $\lambda(U_{\bar t})$. Moreover, testing the eigenvalue equation for $u$ with $v_{\bar t}$ gives
[
\begin{aligned}
\int_{U_{\bar t}}\abs{\nabla v_{\bar t}}^2,dx
&=
\lambda\int_{U_{\bar t}}u v_{\bar t},dx
\
&=
\lambda\norma{v_{\bar t}}{L^2(U{\bar t})}^2
+
\lambda\bar t\int_{U_{\bar t}}v_{\bar t},dx.
\end{aligned}
]
Consequently,
[
\lambda(U_{\bar t})-\lambda
\leq
\lambda\bar t,
\frac{\displaystyle\int_{U_{\bar t}}v_{\bar t},dx}
{\norma{v_{\bar t}}{L^2(U{\bar t})}^2}.
]
By H"older's inequality,
[
\int_{U_{\bar t}}v_{\bar t},dx
\leq
b^{1/2}\norma{v_{\bar t}}{L^2(U{\bar t})}.
]
On the other hand, \autoref{lemma: stime ausiliarie} gives, after reducing $\delta_2$ if necessary,
[
\norma{v_{\bar t}}{L^2(U{\bar t})}^2
\geq
c.
]
It follows that
[
0
\leq
\lambda(U_{\bar t})-\lambda(\Om)
\leq
C\bar t.
]
The last inequality in \eqref{eq: differenza autovalori} follows from \eqref{eq: t bar delta theta}.
\end{proof}

\subsection{Comparison with the model eigenfunction}

\frac{z(,\cdot-x_{\bar t})}{\norma{z}{L^2(B\lambda)}}
}_{L^2(\R^n)}^2.
\end{equation}
\end{oss}

\begin{cor}\label{cor: wt close z}
Under the assumptions of \autoref{teor: main}, provided $\delta$ is sufficiently small, there exists $x_{\bar t}\in\R^n$ such that
\begin{equation}\label{eq: wt close z}
\norma{w_{\bar t}-z(,\cdot-x_{\bar t})}_{L^q(\R^n)}^q
\leq
C\delta^\sigma,
\qquad
\sigma:=\theta\min\left{1,\frac q2\right}.
\end{equation}
\end{cor}

\begin{proof}
Set
[
\widehat w_{\bar t}
:=
\frac{w_{\bar t}}{\norma{w_{\bar t}}{L^2(U{\bar t})}},
\qquad
\widehat z
:=
\frac{z}{\norma{z}{L^2(B\lambda)}}.
]
Combining \eqref{eq: quantitative FK eigenfunctions} with \eqref{eq: differenza autovalori}, we obtain
\begin{equation}\label{eq: AKN L2 normalized}
\norma{\widehat w_{\bar t}-\widehat z(,\cdot-x_{\bar t})}{L^2(\R^n)}^2
\leq C\delta^\theta.
\end{equation}
Both functions are supported on sets of measure $b$. Moreover, the standard $L^2$--$L^\infty$ estimate for Dirichlet eigenfunctions gives
[
\norma{\widehat w{\bar t}}{L^\infty(U{\bar t})}
\leq C_n\lambda(U_{\bar t})^{n/4}
\leq C,
\qquad
\norma{\widehat z}{L^\infty(B\lambda)}\leq C.
]
If $1<q\leq2$, H"older's inequality on the union of the two supports yields
[
\norma{\widehat w_{\bar t}-\widehat z(,\cdot-x_{\bar t})}{L^q}^q
\leq
(2b)^{1-q/2}
\norma{\widehat w{\bar t}-\widehat z(,\cdot-x_{\bar t})}{L^2}^q
\leq C\delta^{q\theta/2}.
]
If $q\geq2$, interpolation with the uniform $L^\infty$ bound gives
[
\norma{\widehat w{\bar t}-\widehat z(,\cdot-x_{\bar t})}{L^q}^q
\leq
C\norma{\widehat w{\bar t}-\widehat z(,\cdot-x_{\bar t})}{L^2}^2
\leq C\delta^\theta.
]
Thus, in both cases,
\begin{equation}\label{eq: AKN Lq normalized}
\norma{\widehat w{\bar t}-\widehat z(,\cdot-x_{\bar t})}_{L^q}^q
\leq C\delta^\sigma.
\end{equation}

The $L^q$ norms of $\widehat w_{\bar t}$ and $\widehat z$ are bounded from below by a positive constant depending only on $n$, $\lambda$ and $q$. For $q\geq2$ this follows from H"older's inequality and the fixed measure of the supports; for $1<q<2$ it follows from their $L^2$ normalization and the uniform $L^\infty$ bound. Applying the elementary normalization estimate
[
\norma{\frac f{\norma f_{L^q}}-\frac g{\norma g_{L^q}}}{L^q}
\leq
\frac{2}{\norma f{L^q}}\norma{f-g}{L^q}
]
and recalling that $w{\bar t}$ and $z$ are $L^q$-normalized, \eqref{eq: wt close z} follows from \eqref{eq: AKN Lq normalized}.
\end{proof}

\norma{u}{L^p(\Om)}^p,
\qquad
\theta:=\min\left{\frac13,\frac{1}{p+1}\right},
\qquad
\sigma:=\theta\min\left{1,\frac q2\right}.
]
Let $w{\bar t}$ be a positive principal Dirichlet eigenfunction of $U_{\bar t}$, normalized by
[
\norma{w_{\bar t}}{L^q(U{\bar t})}=1,
]
and extended by zero outside $U_{\bar t}$. Then there exist two positive constants $\delta_3$ and $C$, depending only on $n$, $\lambda$, $p$ and $q$, such that, if $\delta\leq\delta_3$, then
\begin{equation}\label{eq: u close wt}
\norma{u-w_{\bar t}}_{L^q(\Om)}^q
\leq
C\delta^\sigma.
\end{equation}
\end{prop}

\lambda_1(U_{\bar t})
\norma{v_{\bar t}}{L^2(U{\bar t})}^2.
\end{aligned}
\end{equation}

2^{\frac2n}\lambda.
]
On the other hand, \eqref{eq: differenza autovalori} gives
[
\lambda_1(U_{\bar t})
\leq
\lambda+C\delta^\theta.
]
Therefore, after reducing $\delta_3$ if necessary,
\begin{equation}\label{eq: positive spectral gap}
\lambda_2(U_{\bar t})-\lambda_1(U_{\bar t})
\geq
\frac12\left(2^{\frac2n}-1\right)\lambda
=>0.
\end{equation}

\lambda_1(U_{\bar t})
\norma{v_{\bar t}}{L^2(U{\bar t})}^2
\leq
C\bar t
\leq
C\delta^\theta.
\end{equation}
Combining \eqref{eq: residual spectral gap}, \eqref{eq: residual identity}, \eqref{eq: positive spectral gap} and \eqref{eq: rayleigh residual bound}, we find
\begin{equation}\label{eq: truncation close projection}
\norma{
v_{\bar t}-a_{\bar t}\widehat w_{\bar t}
}{L^2(U{\bar t})}^2
\leq
C\delta^\theta.
\end{equation}

\widehat w_{\bar t}
}{L^2(U{\bar t})}^2
\leq
C\delta^\theta.
\end{equation}

Set
[
\widehat v_{\bar t}
:=
\frac{v_{\bar t}}{\norma{v_{\bar t}}{L^2(U{\bar t})}}.
]
The functions $\widehat v_{\bar t}$ and $\widehat w_{\bar t}$ are supported in $U_{\bar t}$, which has measure $b$, and are uniformly bounded in $L^\infty$. Indeed, the $L^\infty$ bound for $\widehat v_{\bar t}$ follows from Chiti's comparison and the lower bound for $\norma{v_{\bar t}}2$, while the bound for $\widehat w{\bar t}$ follows from the standard eigenfunction estimate and the uniform upper bound for $\lambda(U_{\bar t})$. Thus, arguing exactly as in the proof of \autoref{cor: wt close z}, estimate \eqref{eq: normalized truncation close wt} implies
\begin{equation}\label{eq: normalized truncation close wt Lq}
\norma{\widehat v_{\bar t}-\widehat w_{\bar t}}{L^q(U{\bar t})}^q
\leq C\delta^\sigma.
\end{equation}
The $L^q$ norms of these two $L^2$-normalized functions are bounded from below uniformly. Applying the $L^q$ normalization estimate to \eqref{eq: normalized truncation close wt Lq}, and recalling that $\norma{w_{\bar t}}{L^q}=1$, gives
\begin{equation}\label{eq: Lq normalized truncation close wt}
\norma{
\frac{v{\bar t}}{\norma{v_{\bar t}}{L^q(U{\bar t})}}
-w_{\bar t}
}{L^q(U{\bar t})}^q
\leq C\delta^\sigma.
\end{equation}

It remains to remove the truncation. By \eqref{eq: Lq truncation error},
[
\norma{u-v_{\bar t}}{L^q(\Om)}^q
\leq C\delta^\theta.
]
Since $\norma u{L^q}=1$, the reverse triangle inequality yields
[
\left|1-\norma{v_{\bar t}}{L^q}\right|
\leq
\norma{u-v{\bar t}}{L^q}.
]
Consequently,
\begin{equation}\label{eq: u close Lq normalized truncation}
\norma{
u-
\frac{v{\bar t}}{\norma{v_{\bar t}}{L^q(U{\bar t})}}
}_{L^q(\Om)}^q
\leq C\delta^\theta
\leq C\delta^\sigma.
\end{equation}
Finally, \eqref{eq: u close wt} follows from \eqref{eq: Lq normalized truncation close wt}, \eqref{eq: u close Lq normalized truncation}, and the triangle inequality.
\end{proof}

\begin{proof}[Proof of \autoref{teor: main}]
By \autoref{cor: wt close z}, there exists $x_0\in\R^n$ such that
[
\norma{w_{\bar t}-z(,\cdot-x_0)}{L^q(\R^n)}^q
\leq
C\delta^\sigma.
]
On the other hand, \autoref{prop: closeness u wt} gives
[
\norma{u-w{\bar t}}{L^q(\R^n)}^q
\leq
C\delta^\sigma.
]
Therefore, by the triangle inequality,
[
\norma{u-z(,\cdot-x_0)}{L^q(\R^n)}^q
\leq
2^{q-1}\left(
\norma{u-w_{\bar t}}{L^q}^q
+
\norma{w{\bar t}-z(,\cdot-x_0)}_{L^q}^q
\right)
\leq C\delta^\sigma.
]
This proves \eqref{eq: main eigenfunction stability}.
\end{proof}

\norma{u^-z^}{L^q(0,\abs{\Om})}^q
\leq
C\delta^\beta,
\qquad
\beta:=\min\left{\frac12,\frac qp\right}.
]
Since $\beta\geq\theta\geq\sigma$ and $\delta\leq1$, the right-hand side is bounded by $C\delta^\sigma$.
Let $x_0\in\R^n$ be the point provided by \autoref{teor: main}. By translation invariance, the preceding estimate gives
[
\norma{u^\sharp(,\cdot-x_0)-z(,\cdot-x_0)}{L^q(\R^n)}^q
\leq
C\delta^\sigma.
]
Combining this estimate with \eqref{eq: main eigenfunction stability} and using the triangle inequality, we obtain
[
\norma{u-u^\sharp(,\cdot-x_0)}_{L^q(\R^n)}^q
\leq
C\delta^\sigma.
]
This proves \eqref{eq: Lq almost symmetry}.
\end{proof}

\section{Sobolev stability in the range \texorpdfstring{$1<q\leq2$}{1<q<=2}}

Throughout this section we assume $1<q\leq2$ and use the notation of
\autoref{teor: main}. We also set
[
\beta:=\min\left{\frac12,\frac qp\right}.
]
Recall that $\beta\geq\theta$.

We first recover the $L^2$-normalized estimates which are needed in the
gradient argument. This step is independent of the conversion from $L^2$ to
$L^q$ used in the proof of \autoref{teor: main}.

\begin{lemma}\label{lemma: L2 normalized stability}
Let
[
\widehat u:=\frac{u}{\norma{u}{L^2(\Om)}},
\qquad
\widehat z:=\frac{z}{\norma{z}{L^2(B_\lambda)}},
\qquad
\widehat{u^\sharp}:=\frac{u^\sharp}{\norma{u^\sharp}{L^2(\Om^\sharp)}}.
]
There exists $x_0\in\R^n$ such that
\begin{equation}\label{eq: three L2 normalized estimates}
\begin{aligned}
&\norma{\widehat u-\widehat z(,\cdot-x_0)}{L^2(\R^n)}^2
+
\norma{\widehat{u^\sharp}-\widehat z}{L^2(\R^n)}^2
\
&\qquad+
\norma{\widehat u-\widehat{u^\sharp}(,\cdot-x_0)}{L^2(\R^n)}^2
\leq C\delta^\theta.
\end{aligned}
\end{equation}
Moreover, the $L^2$ norms of $u$, $u^\sharp$ and $z$ are bounded from above
and below by positive constants depending only on the fixed parameters.
\end{lemma}

\begin{proof}
The upper bounds follow from Chiti's $L^\infty$ comparison and the $L^q$
normalization. The lower bound for $u$ follows from
\eqref{eq: truncation L2 lower bound}, while the corresponding statements for
$u^\sharp$ and $z$ are immediate.

Let $v_{\bar t}=(u-\bar t)+$. Since
$u\leq\norma{z}{L^\infty(B_\lambda)}$ and
$u^\leq\bar t$ on $(b,\abs\Om)$, estimates \eqref{eq: Lq tail} and
\eqref{eq: t bar delta theta} give
\begin{equation}\label{eq: L2 truncation error Sobolev}
\begin{aligned}
\norma{u-v_{\bar t}}_{L^2(\Om)}^2
&=
b\bar t^2+
\int_b^{\abs\Om}(u^)^2,ds
\
&\leq
b\bar t^2+
\bar t^{2-q}\int_b^{\abs\Om}(u^*)^q,ds
\leq C\delta^\theta.
\end{aligned}
\end{equation}
Here and below the case $q=2$ is understood with $\bar t^{2-q}=1$.
The normalization estimate, \eqref{eq: normalized truncation close wt}, and
\eqref{eq: AKN L2 normalized} therefore imply, for the point $x_0$ supplied
by the quantitative Faber--Krahn estimate,
[
\norma{\widehat u-\widehat z(,\cdot-x_0)}_{L^2(\R^n)}^2
\leq C\delta^\theta.
]

On the other hand,
$\abs{u^\sharp-z}\leq2\norma{z}{L^\infty(B\lambda)}$ and
\eqref{eq: Lq rearrangements} yield
[
\norma{u^\sharp-z}{L^2(\R^n)}^2
\leq
(2\norma{z}{L^\infty(B_\lambda)})^{2-q}
\norma{u^\sharp-z}_{L^q(\R^n)}^q
\leq C\delta^\beta
\leq C\delta^\theta.
]
After normalization this gives the second estimate in
\eqref{eq: three L2 normalized estimates}. The third one follows from the
first two estimates and the triangle inequality.
\end{proof}

The next estimate is the quantitative P'olya--Szeg\H{o} deficit used in the
old $H^1$ argument.

\int_{\Om^\sharp}\abs{\nabla u^\sharp}^2,dx
\leq C\delta^\theta.
\end{equation}
The same estimate holds for the $L^2$-normalized functions.
\end{lemma}

\int_{\Om^\sharp}\abs{\nabla u^\sharp}^2
\
&\leq
\lambda\left(\int_\Om u^2-\int_{B_\lambda}v^2\right)
\
&=
\lambda\left[
2\bar t\int_0^b u^(s),ds-b\bar t^2
+
\int_b^{\abs\Om}(u^)^2,ds
\right].
\end{aligned}
]
The first term is bounded by $C\bar t$, while the last one is bounded as in
\eqref{eq: L2 truncation error Sobolev}. This proves
\eqref{eq: Polya Szego deficit}. Since $u$ and $u^\sharp$ have the same
$L^2$ norm and this norm is bounded from below, division by that norm proves
the normalized version.
\end{proof}

We now correct and record the integration-by-parts part of the $H^1$
argument. In particular, the quantities on the left-hand side below are
squared gradient norms.

\begin{lemma}\label{lemma: H1 almost symmetry}
For the point $x_0$ in \autoref{lemma: L2 normalized stability},
\begin{equation}\label{eq: H1 almost symmetry corrected}
\norma{\nabla u-
\nabla u^\sharp(,\cdot-x_0)}{L^2(\R^n)}^2
\leq C\delta^{\theta/3},
\end{equation}
and
\begin{equation}\label{eq: H1 radial model corrected}
\norma{\nabla u^\sharp-\nabla z}{L^2(\R^n)}^2
\leq C\delta^\theta.
\end{equation}
\end{lemma}

\begin{proof}
Write
$a=\norma{u}{L^2(\Om)}=\norma{u^\sharp}{L^2(\Om^\sharp)}$ and
$c=\norma{z}{L^2(B\lambda)}$. By
\autoref{lemma: L2 normalized stability}, both numbers are bounded above and
below. Let
[
U:=\frac{u^\sharp}{a},
\qquad
Z:=\frac zc.
]
Both functions have unit $L^2$ norm. Since $Z$ is radial, its outer normal
derivative on $\partial B_\lambda$ is a negative constant, denoted by
$Z_N$. The P'olya--Szeg\H{o} inequality and integration by parts on
$B_\lambda$ give
\begin{align*}
\norma{\nabla U-\nabla Z}{L^2(\R^n)}^2
&\leq
2\lambda-2\int{B_\lambda}\nabla U\cdot\nabla Z,dx
\
&=
2\lambda-2\lambda\int_{B_\lambda}UZ,dx
-2Z_N\int_{\partial B_\lambda}U,d\mathcal H^{n-1}
\
&=
\lambda\norma{U-Z}{L^2(\R^n)}^2
-2Z_N\abs{\partial B\lambda}\frac{\bar t}{a}
\leq C\delta^\theta.
\end{align*}
In the last line we used \eqref{eq: three L2 normalized estimates} and
\eqref{eq: t bar delta theta}. Furthermore,
[
\abs{a-c}
\leq
\norma{u^\sharp-z}{L^2(\R^n)}
\leq C\delta^{\beta/2}.
]
Consequently,
[
\norma{\nabla u^\sharp-\nabla z}{L^2(\R^n)}
\leq
a\norma{\nabla U-\nabla Z}{L^2(\R^n)}
+\abs{a-c}\norma{\nabla Z}{L^2(\R^n)},
]
which proves \eqref{eq: H1 radial model corrected}.

\int_{\R^n}(Z_0-G)h
+
\int_{\R^n}G(F-G),
\qquad
\int_{\R^n}G(F-G)=-\frac12H^2,
]
and hence it is bounded by $C\delta^\theta$.

The interpolation trace inequality on the fixed ball $B_0$ yields
[
\norma{h}{L^2(\partial B_0)}
\leq
C\norma{h}{L^2(B_0)}^{1/2}\norma{h}_{H^1(B_0)}^{1/2}
\leq
C H^{1/2}(H^2+X)^{1/4}.
]
Using Young's inequality,
[
H^{1/2}(H^2+X)^{1/4}
\leq
CH+CH^{1/2}X^{1/4}
\leq
CH+CH^{2/3}+\frac18X.
]
Combining these estimates with \eqref{eq: X preliminary Sobolev} and using
$H\leq C\delta^{\theta/2}$, we obtain
[
X\leq C\delta^{\theta/3}.
]
Finally, multiplying by the uniformly bounded factor $a$ proves
\eqref{eq: H1 almost symmetry corrected}.
\end{proof}

To pass from $H^1$ to $W^{1,q}$ without introducing a factor depending on
$\abs\Om$, we need a separate estimate on the low-level tail.

\begin{lemma}\label{lemma: W1q gradient tail}
Set
[
\eta:=\min{u,\bar t},
\qquad
\eta^\sharp:=\min{u^\sharp,\bar t}.
]
Then
\begin{equation}\label{eq: L2 gradient tail}
\norma{\nabla\eta}{L^2(\R^n)}^2
+
\norma{\nabla\eta^\sharp}{L^2(\R^n)}^2
\leq C\delta^\theta
\end{equation}
and
\begin{equation}\label{eq: Lq gradient tail}
\norma{\nabla\eta}{L^q(\R^n)}^q
+
\norma{\nabla\eta^\sharp}{L^q(\R^n)}^q
\leq C\delta^{q\theta/6}.
\end{equation}
\end{lemma}

\lambda\left(
\int_{{u<\bar t}}u^2,dx
+\bar t\int_{{u\geq\bar t}}u,dx
\right).
]
The first term is at most
[
\bar t^{2-q}\int_b^{\abs\Om}(u^*)^q,ds,
]
while the second one is bounded by $C\bar t$, because
$\abs{{u\geq\bar t}}=b$. Thus \eqref{eq: Lq tail} and
\eqref{eq: t bar delta theta} give
[
\norma{\nabla\eta}_{L^2(\R^n)}^2\leq C\delta^\theta.
]
Since rearrangement commutes with truncation, the P'olya--Szeg\H{o}
inequality gives the same estimate for $\eta^\sharp$, proving
\eqref{eq: L2 gradient tail}.

\lambda\left(
\int_{{u<\bar t}}u^q,dx
+\bar t^{q-1}\int_{{u\geq\bar t}}u,dx
\right)
\leq C\delta^{(q-1)\theta}.
\end{equation}
Here we used $\beta\geq\theta>(q-1)\theta$. By H"older's inequality,
\begin{align*}
\int_{{u<\bar t}}\abs{\nabla u}^q,dx
&\leq
\left(
\int_{{u<\bar t}}u^{q-2}\abs{\nabla u}^2,dx
\right)^{q/2}
\left(
\int_{{u<\bar t}}u^q,dx
\right)^{(2-q)/2}
\
&\leq
C\delta^{\frac{q(q-1)}2\theta+\frac{2-q}{2}\beta}
\leq C\delta^{q\theta/6}.
\end{align*}
For the last inequality we used $\beta\geq\theta$ and
[
\frac12(q^2-2q+2)\geq\frac q6,
\qquad 1<q<2.
]

Finally, set
[
\Phi(s):=\frac2q\min{s,\bar t}^{q/2}.
]
Since $\Phi(u)^\sharp=\Phi(u^\sharp)$, the P'olya--Szeg\H{o} inequality
applied to $\Phi(u)$ shows that the weighted integral on the left-hand side
of \eqref{eq: weighted gradient tail} does not increase under
rearrangement. The same H"older argument therefore proves the estimate for
$\eta^\sharp$.
\end{proof}

\begin{proof}[Proof of \autoref{teor: W1q stability}]
Let $x_0$ be the point in \autoref{lemma: H1 almost symmetry}, and set
[
v:=(u-\bar t)+,
\qquad
v^\sharp:=(u^\sharp-\bar t)+.
]
The supports of $v$ and $v^\sharp(,\cdot-x_0)$ have measure $b$. By
\eqref{eq: H1 almost symmetry corrected} and
\eqref{eq: L2 gradient tail},
[
\norma{\nabla v-
\nabla v^\sharp(,\cdot-x_0)}{L^2(\R^n)}
\leq C\delta^{\theta/6}.
]
H"older's inequality on the union of the two supports, whose measure is at
most $2b$, yields
[
\norma{\nabla v-
\nabla v^\sharp(,\cdot-x_0)}{L^q(\R^n)}^q
\leq C\delta^{q\theta/6}.
]
Adding back the two tails and using \eqref{eq: Lq gradient tail}, we obtain
\begin{equation}\label{eq: W1q almost symmetry}
\norma{\nabla u-
\nabla u^\sharp(,\cdot-x_0)}_{L^q(\R^n)}^q
\leq C\delta^{q\theta/6}.
\end{equation}

Similarly, $v^\sharp$ and $z$ are supported in $B_\lambda$. Estimates
\eqref{eq: H1 radial model corrected} and \eqref{eq: L2 gradient tail}
give
[
\norma{\nabla v^\sharp-\nabla z}{L^2(\R^n)}
\leq C\delta^{\theta/2}.
]
Using H"older's inequality on $B\lambda$ and then adding back
$\eta^\sharp$, we find
\begin{equation}\label{eq: W1q rearranged model}
\norma{\nabla u^\sharp-\nabla z}{L^q(\R^n)}^q
\leq C\delta^{q\theta/6}.
\end{equation}
The zero-order terms are better: \eqref{eq: Lq almost symmetry} and
\eqref{eq: Lq rearrangements}, together with $\beta\geq\theta$, imply
[
\norma{u-u^\sharp(,\cdot-x_0)}{L^q}^q
+
\norma{u^\sharp-z}_{L^q}^q
\leq C\delta^{q\theta/6}.
]
Combining this estimate with \eqref{eq: W1q almost symmetry} and
\eqref{eq: W1q rearranged model}, and translating the latter by $x_0$,
proves \eqref{eq: W1q eigenfunction stability}.
\end{proof}



\printbibliography
\end{document}
```

### Assistant response to Prompt 1

> **Archival note.** This response was originally delivered in English as a PDF, so no translation is required here. For continuity of the prompt history, a plain-text transcription of that output is included directly below. The original rendered output is also preserved as [`outputs/output_01_quantitative_kohler_jobin_level_sets.pdf`](outputs/output_01_quantitative_kohler_jobin_level_sets.pdf). The PDF was originally named `k_j (2).pdf`; only the filename has been changed for clarity.

```text
A quantitative Kohler–Jobin argument through level sets
1 The general idea
For a bounded open set D ⊂ Rn, let
λ1(D) = min
0̸=φ∈H1
0 (D)
∫︂
D
|∇φ|2
dx
∫︂
D
φ2
dx
be the first Dirichlet eigenvalue, and let
T(D) = max
0̸=φ∈H1
0 (D)
(︃∫︂
D
φ dx
)︃2
∫︂
D
|∇φ|2
dx
be the torsional rigidity.
If wD denotes the torsion function,
−∆wD = 1 in D, wD ∈ H1
0 (D),
then
T(D) =
∫︂
D
wD dx =
∫︂
D
|∇wD|2
dx.
The Kohler–Jobin inequality states that
λ1(Ω)T(Ω)
n+2
is minimized by balls.
The aim of this note is to explain how a small Kohler–Jobin deficit can be converted into
a small Faber–Krahn deficit on a suitable superlevel set of the first eigenfunction.
The architecture is closely related to the one appearing in a quantitative version of Chiti’s
inequality: one first controls the level structure of the eigenfunction, then chooses a level whose
superlevel set has the correct volume, and finally uses the truncation of the eigenfunction as a
competitor for the first eigenvalue of this superlevel set.
The main difference lies in the mechanism producing the initial control on the levels. In
the Chiti setting this comes from the single-crossing property of rearrangements. Here it
comes from the Kohler–Jobin rearrangement and the modified torsional rigidity.
2 Normalization
For balls we write
T(BR) = τnRn+2
, λ1(BR) = ΛnR−2
,

where
τn := T(B1), Λn := λ1(B1).
Since
T(rD) = rn+2
T(D), λ1(rD) = r−2
λ1(D),
the quantity
λ1(D)T(D)
n+2
is scale invariant.
We may therefore normalize
T(Ω) = T(B1) = τn.
We write
λ1(Ω) = Λn(1 + δ),
so that
δ =
λ1(Ω)
λ1(B1)
− 1
is the normalized Kohler–Jobin deficit.
Let u > 0 be the first eigenfunction of Ω, normalized by
∥u∥L2(Ω) = 1.
Thus
−∆u = λ1(Ω)u in Ω.
We shall show that a small value of δ produces a suitable superlevel set of u with small
Faber–Krahn deficit.
3 Modified torsional rigidity
The Kohler–Jobin rearrangement does not use the full torsional problem directly. Instead,
one restricts the admissible functions to functions depending only on u, namely functions of
the form
g(u).
This gives the modified torsional rigidity
Tmod(Ω; u).
Since the admissible class is smaller than H1
0 (Ω),
Tmod(Ω; u) ≤ T(Ω) = τn.
Let Br be the ball such that
T(Br) = Tmod(Ω; u). (1)
Since T(Br) = τnrn+2, we have
r ≤ 1.
The importance of this ball is that it is precisely the comparison ball naturally produced
by the Kohler–Jobin rearrangement.

4 The Kohler–Jobin rearrangement
Starting from u, the Kohler–Jobin construction produces a radial decreasing function
v ∈ H1
0 (Br)
such that ∫︂
Br
|∇v|2
dx =
∫︂
Ω
|∇u|2
dx = λ1(Ω), (2)
and, in particular, ∫︂
Br
v2
dx ≥
∫︂
Ω
u2
dx = 1. (3)
Set
A :=
∫︂
Br
v2
dx.
Then
A ≥ 1.
Using v as a competitor in the Rayleigh quotient of Br, we obtain
λ1(Br) ≤
∫︂
Br
|∇v|2
dx
∫︂
Br
v2
dx
=
λ1(Ω)
A
.
Since
λ1(Br) = Λnr−2
, λ1(Ω) = Λn(1 + δ),
we get
A
r2
≤ 1 + δ.
Since A ≥ 1 and r ≤ 1, it follows that
0 ≤ A − 1 ≤ δ (4)
and
(1 + δ)−1/2
≤ r ≤ 1. (5)
Thus the first quantitative information supplied by the Kohler–Jobin deficit is the estimate
A − 1 ≤ δ.
The quantity A − 1 measures the L2-mass gained by the Kohler–Jobin rearrangement.
Moreover, from (5),
0 ≤ T(Ω) − Tmod(Ω; u) = τn(1 − rn+2
) ≤ Cnδ.

5 The superlevel structure
Set
M := ∥u∥L∞(Ω)
and define
µ(t) := |{u > t}|, 0 ≤ t ≤ M.
We also write
Ωt := {u > t}.
For each t, consider the truncation
(u − t)+.
We define
T (t) := Tmod
(︁
Ωt; (u − t)+
)︁
.
The point of this definition is that T (t) measures the modified torsional rigidity remaining
above the level t.
Let
F(t) :=
∫︂
{u>t}
u dx.
Integrating
−∆u = λ1(Ω)u
over the superlevel set {u > t} gives, for almost every t,
∫︂
{u=t}
|∇u| dHn−1
= λ1(Ω)F(t). (6)
Using the level-set representation of the modified torsion, one finds
T (t) =
∫︂ M
t
µ(s)2
λ1(Ω)F(s)
ds. (7)
Therefore
−T ′
(t) =
µ(t)2
λ1(Ω)F(t)
(8)
for almost every t.
6 The comparison volume β(t)
For every t, define β(t) to be the volume of the ball having torsional rigidity T (t).
Since
T(Bρ) = τnρn+2
, |Bρ| = ωnρn
,
we have
β(t) = ωn
(︃
T (t)
τn
)︃ n
n+2
. (9)
At t = 0,
T (0) = Tmod(Ω; u) = T(Br),
hence
β(0) = |Br|.

We set
b := |Br|.
A fundamental comparison gives
β(t) ≤ µ(t). (10)
This has a simple interpretation. The set Ωt has volume µ(t), while T (t) is no larger than
its usual torsional rigidity. By the Saint–Venant inequality, the ball of volume µ(t) maximizes
torsion. Hence the ball having torsion T (t) cannot have volume larger than µ(t).
7 The displacement of the levels
We now compare the levels of u with those of the radial function v produced by the Kohler–
Jobin rearrangement.
Let
Φ(t)
be the level of v corresponding to the level t of u.
The construction gives
|{v > Φ(t)}| = β(t).
Moreover,
Φ′
(t) =
µ(t)
β(t)
(11)
for almost every t.
Because of (10),
Φ′
(t) ≥ 1.
We define the displacement function
D(t) := Φ(t) − t.
Since
Φ(0) = 0,
we have
D(0) = 0.
Furthermore,
D′
(t) =
µ(t)
β(t)
− 1 ≥ 0. (12)
Thus D is nondecreasing.
This is one of the key structural properties of the construction. Once a positive displacement
between the levels of u and those of v has accumulated, it persists at all higher levels.

8 An exact identity for the L2
-gain
By the layer-cake formula, ∫︂
Ω
u2
dx = 2
∫︂ M
0
tµ(t) dt.
For v, ∫︂
Br
v2
dx = 2
∫︂ ∞
0
s|{v > s}| ds.
Using the change of variables
s = Φ(t),
together with
|{v > Φ(t)}| = β(t)
and
Φ′
(t) =
µ(t)
β(t)
,
we obtain ∫︂
Br
v2
dx = 2
∫︂ M
0
Φ(t)β(t)Φ′
(t) dt
= 2
∫︂ M
0
Φ(t)µ(t) dt.
Subtracting the corresponding formula for u, and recalling ∥u∥2 = 1, we find
A − 1 = 2
∫︂ M
0
D(t)µ(t) dt. (13)
Combining (13) with (4) gives
∫︂ M
0
D(t)µ(t) dt ≤ δ. (14)
This is the quantitative level-set information hidden in the Kohler–Jobin deficit.
9 The distinguished level t̄
We now choose the level at which the superlevel set has exactly the same volume as Br.
Define
t̄ := u∗
(b), b = |Br|. (15)
Thus
|{u > t̄}| = b = |Br|. (16)
Set
U := {u > t̄}.
The reason for choosing t̄ in this way is that U and Br have the same volume, so that the
Faber–Krahn inequality, and later its quantitative form, can be applied directly to the pair
(U, Br).
The remaining task is to show that t̄ is small when δ is small.

10 Uniform bounds on the eigenfunction
We first collect two elementary estimates.
Using u as a competitor in the variational characterization of torsion,
T(Ω) ≥
(︁∫︁
Ω u dx
)︁2
∫︁
Ω |∇u|2 dx
.
Since
T(Ω) = τn,
∫︂
Ω
|∇u|2
dx = λ1(Ω),
we obtain
∥u∥2
L1(Ω) ≤ τnλ1(Ω). (17)
For δ ≤ 1, this gives
∥u∥L1(Ω) ≤ Cn.
We shall also use the standard L∞ bound for a L2-normalized first eigenfunction,
∥u∥L∞(Ω) ≤ Cnλ1(Ω)n/4
≤ Cn (18)
for bounded δ.
11 Quadratic growth of the level displacement
For
0 ≤ t ≤ t̄,
the definition of t̄ gives
µ(t) ≥ b. (19)
From (5), for δ ≤ 1,
b = |Br| ≥ cn > 0.
Using (8), (19), and
F(t) ≤ ∥u∥L1(Ω),
we obtain
−T ′
(t) =
µ(t)2
λ1(Ω)F(t)
≥ cn
for
0 ≤ t ≤ t̄.
Integrating,
T (0) − T (t) ≥ cnt. (20)
Recall that
β(t) = ωn
(︃
T (t)
τn
)︃ n
n+2
.
Since T (0) is uniformly bounded away from zero when δ is small, (20) implies
b − β(t) ≥ cnt. (21)
Now
D′
(t) =
µ(t) − β(t)
β(t)
.

Using µ(t) ≥ b,
D′
(t) ≥
b − β(t)
b
≥ cnt.
Since D(0) = 0,
D(t) ≥ cnt2
, 0 ≤ t ≤ t̄. (22)
12 A lower bound on the mass above small levels
For t ≥ 0, set
gt := (u − t)+.
Pointwise,
0 ≤ u2
− g2
t ≤ 2tu.
Hence
∥gt∥2
2 ≥ 1 − 2t∥u∥1.
Using the uniform L1 bound, there exists
t0 = t0(n) > 0
such that
t ≤ t0 =⇒ ∥gt∥2
2 ≥
. (23)
Moreover,
∥gt∥∞ ≤ ∥u∥∞ ≤ Cn.
Therefore ∫︂
Ω
gt dx ≥
∥gt∥2
∥gt∥∞
≥ cn.
By the layer-cake formula,
∫︂
Ω
gt dx =
∫︂ M
t
µ(s) ds.
Thus
∫︂ M
t
µ(s) ds ≥ cn (24)
for every t ≤ t0.
13 Estimate of the truncation level
We can now estimate t̄.
Proposition 13.1. There exist constants Cn > 0 and δ0 > 0 such that, if
δ ≤ δ0,
then
t̄2
≤ Cnδ.

Proof. Assume first that
t̄ ≤ t0.
Since D is nondecreasing, (13) gives
A − 1 = 2
∫︂ M
0
D(s)µ(s) ds
≥ 2
∫︂ M
t̄
D(s)µ(s) ds
≥ 2D(t̄)
∫︂ M
t̄
µ(s) ds.
By (22) and (24),
A − 1 ≥ cnt̄2
.
Using A − 1 ≤ δ, we conclude that
t̄2
≤ Cnδ.
Suppose now that
t̄ > t0.
Applying exactly the same argument at the fixed level t0, we obtain
A − 1 ≥ cnt2
0.
Since A − 1 ≤ δ, this is impossible if δ0 is chosen sufficiently small.
Hence, for small deficit,
t̄ ≤ t0,
and the previous estimate applies.
In particular,
t̄ ≤ Cnδ1/2
. (25)
14 The Faber–Krahn deficit of the core
Recall
U = {u > t̄}
and define
g := (u − t̄)+.
By construction,
|U| = |Br|.
We first compare g with u. Since
u − g = min{u, t̄},
we have
∥u − g∥2
2 =
∫︂
Ω
min{u, t̄}2
dx
≤ t̄
∫︂
Ω
u dx.

Using (17) and (25),
∥u − g∥2
2 ≤ Cnδ1/2
. (26)
In particular, for small deficit,
∥g∥2
is uniformly bounded from below.
We now test
−∆u = λ1(Ω)u
with g.
On U,
u = g + t̄.
Thus ∫︂
U
|∇g|2
dx = λ1(Ω)
∫︂
U
ug dx
= λ1(Ω)
(︃∫︂
U
g2
dx + t̄
∫︂
U
g dx
)︃
.
Using g as a competitor for λ1(U), we obtain
λ1(U) ≤ λ1(Ω) + λ1(Ω)t̄
∫︂
U
g dx
∫︂
U
g2
dx
.
The quotient on the right-hand side is uniformly bounded. Therefore
λ1(U) ≤ λ1(Ω) + Cnt̄. (27)
On the other hand, since
|U| = |Br|,
the Faber–Krahn inequality gives
λ1(U) ≥ λ1(Br).
Therefore
0 ≤ λ1(U) − λ1(Br)
≤ λ1(Ω) − λ1(Br) + Cnt̄.
Since r ≤ 1,
λ1(Br) ≥ Λn,
and hence
λ1(Ω) − λ1(Br) ≤ λ1(Ω) − Λn = Λnδ.
Using t̄ ≤ Cnδ1/2, we obtain
0 ≤ λ1(U) − λ1(Br) ≤ Cnδ1/2
. (28)
Thus a small Kohler–Jobin deficit produces a superlevel set having small Faber–Krahn
deficit.
This is the central reduction.

15 Quantitative Faber–Krahn stability
Let
RD := (−∆D)−1
denote the Dirichlet resolvent, with solutions extended by zero outside D.
A quantitative Faber–Krahn estimate for the resolvent gives, for two sets of equal volume,
λ1(D) − λ1(B) ≥ cn inf
x∈Rn
∥RD − RB(x)∥2
L∞→L2 ,
up to the appropriate scaling factor.
Applying this to U and Br, and using (28), we find
inf
x∈Rn
∥RU − RBr(x)∥2
L∞→L2 ≤ Cnδ1/2
. (29)
Hence
inf
x
∥RU − RBr(x)∥L∞→L2 ≤ Cnδ1/4
.
This is the first place where the final power 4 appears.
16 Comparison between Ω and the core
We now show that U carries almost all the torsional rigidity of Ω.
Applying the classical Kohler–Jobin inequality to U,
λ1(U)T(U)
n+2 ≥ Λnτ
n+2
n .
Since
λ1(U) ≤ Λn + Cnδ1/2
,
we obtain
T(U) ≥ τn − Cnδ1/2
.
As
U ⊂ Ω,
torsional rigidity is monotone, so
T(U) ≤ T(Ω) = τn.
Consequently
0 ≤ T(Ω) − T(U) ≤ Cnδ1/2
. (30)
We use the following elementary fact.
Lemma 16.1. Let D ⊂ E be bounded open sets. Then
∥RE − RD∥2
L∞→L2 ≤
T(E) − T(D)
λ1(E)
.
Proof. Let wE and wD denote the torsion functions. By positivity and domain monotonicity
of the Dirichlet resolvent, for every f with
∥f∥∞ ≤ 1,
we have
|(RE − RD)f| ≤ wE − wD.

Hence
∥RE − RD∥L∞→L2 ≤ ∥wE − wD∥2.
Moreover, extending wD by zero outside D,
∫︂
E
∇wE · ∇wD dx =
∫︂
E
wD dx = T(D).
Therefore
∥∇(wE − wD)∥2
2 = T(E) + T(D) − 2T(D)
= T(E) − T(D).
Finally, by Poincaré’s inequality on E,
∥wE − wD∥2
2 ≤
λ1(E)
∥∇(wE − wD)∥2
2.
Combining the estimates proves the claim.
Applying Lemma 16.1 to
U ⊂ Ω
and using (30), we obtain
∥RΩ − RU ∥2
L∞→L2 ≤ Cnδ1/2
. (31)
Thus
∥RΩ − RU ∥L∞→L2 ≤ Cnδ1/4
.
17 Comparison between Br and B1
From (5),
1 − r ≤ Cnδ.
Hence
T(B1) − T(Br) = τn(1 − rn+2
) ≤ Cnδ.
Since
Br(x) ⊂ B1(x),
Lemma 16.1 yields
∥RB1(x) − RBr(x)∥2
L∞→L2 ≤ Cnδ. (32)
Therefore
∥RB1(x) − RBr(x)∥L∞→L2 ≤ Cnδ1/2
.
18 Conclusion
Choose a translation x for which (29) holds. By the triangle inequality,
∥RΩ − RB1(x)∥L∞→L2 ≤ ∥RΩ − RU ∥L∞→L2
+ ∥RU − RBr(x)∥L∞→L2
+ ∥RBr(x) − RB1(x)∥L∞→L2 .
Using (29), (31), and (32),
inf
x∈Rn
∥RΩ − RB1(x)∥L∞→L2 ≤ Cnδ1/4
.

Equivalently,
δ ≥ cn
(︃
inf
x∈Rn
∥RΩ − RB1(x)∥L∞→L2
)︃4
. (33)
Returning to the original scale, let BT be a ball satisfying
T(BT ) = T(Ω)
and denote its radius by RT . Since
∥RrD∥L∞→L2 = r
n
+2
∥RD∥L∞→L2 ,
the scale-invariant form of (33) is
δKJ(Ω) ≥ cn
[︃
R
−n+4
T inf
x∈Rn
∥RΩ − RBT (x)∥L∞→L2
]︃4
.
19 Where the exponent is lost
The origin of the fourth power can now be seen explicitly.
First,
A − 1 ≲ δ.
The level-set identity and the quadratic growth of D yield
t̄2
≲ δ,
hence
t̄ ≲ δ1/2
.
The Faber–Krahn deficit of the core then satisfies
λ1(U) − λ1(Br) ≲ δ + t̄ ≲ δ1/2
.
Finally, quantitative Faber–Krahn stability gives
dres(U, Br)2
≲ λ1(U) − λ1(Br),
and consequently
dres(U, Br) ≲ δ1/4
.
Thus
δ ≳ d4
res.
The loss therefore does not come from the quantitative Faber–Krahn theorem itself. It
occurs earlier, in the estimate
t̄2
≲ δ.
A sharp quadratic resolvent stability estimate would require a mechanism avoiding this
square-root loss.

20 Relation with the quantitative Chiti argument
The structure is now transparent.
In a quantitative Chiti argument one has schematically
single crossing + norm deficit −→ control of the rearrangements,
which is then converted into
t̄ small −→ Ut̄ almost optimal for Faber–Krahn.
In the present Kohler–Jobin argument, the first part is replaced by
modified torsion + Kohler–Jobin rearrangement −→ A − 1 ≤ δ,
followed by the exact identity
A − 1 = 2
∫︂ M
0
D(t)µ(t) dt.
Thus the correspondence is
control of u∗
− z∗
←→ A − 1 = 2
∫︂
Dµ.
After the control of the levels has been obtained, both arguments follow the same basic
mechanism:
level control −→ t̄ small −→ Ut̄ has small FK deficit −→ quantitative Faber–Krahn stability.
References
[1] L. Brasco, On torsional rigidity and principal frequencies: an invitation to the Kohler–
Jobin rearrangement technique, ESAIM Control Optim. Calc. Var. 20 (2014), no. 2,
315–338.
[2] M.-T. Kohler-Jobin, Symmetrization with equal Dirichlet integrals, SIAM J. Math. Anal.
13 (1982), 153–161.
[3] M. Allen, D. Kriventsov, R. Neumayer, Quantitative Resolvent and Eigenfunction Stability
for the Faber–Krahn Inequality, arXiv:2504.13053.
[4] G. Chiti, A reverse Hölder inequality for the eigenfunctions of linear second order elliptic
operators, Z. Angew. Math. Phys. 33 (1982), 143–148.
```

## Prompt 2 — English translation

In my view, the technique used in the Chiti argument to estimate \(\bar t\) is not the best possible one. I am convinced that the exponent can be improved at that step by using results from Brasco's paper.

### Assistant response to Prompt 2 — English translation

Yes. In the analogous Kohler--Jobin step, copying the Chiti estimate
\[
\|z^*-u^*\|_2^2\gtrsim \bar t^3
\]
artificially loses one power: in your Chiti proof, the cubic power comes precisely from the boundary strip of width \(h\sim\bar t\).

In the Kohler--Jobin case, instead, Brasco provides a much more suitable variable: the modified torsional rigidity of the superlevel sets. Proposition 3.5 gives the explicit formula for \(T_{\rm mod}\), while Proposition 4.1 simultaneously parametrizes \(u\) and its Kohler--Jobin rearrangement through the torsion of the superlevel sets; in particular, identities (4.3)--(4.6) appear, and these are exactly the relations needed here. [Cvgmt](https://cvgmt.sns.it/media/doc/paper/2083/KJp_rev.pdf)

For small deficit, the resulting estimate is
\[
\boxed{\bar t^2\lesssim
\frac{\lambda_1(\Omega)}{\lambda_1(B_r)}-1
\lesssim \delta_{\rm KJ}},
\qquad\text{hence}\qquad
\boxed{\bar t\lesssim\delta_{\rm KJ}^{1/2}.}
\]
It is preferable not to replace the first deficit immediately by \(\delta_{\rm KJ}\): decomposing it into two distinct deficits preserves more information.

```latex
\subsection{An improved estimate for the distinguished level}

The estimate for the distinguished level should not be obtained by
repeating the boundary-strip argument used in the quantitative Chiti
inequality.  In the present setting the Kohler--Jobin rearrangement
provides a more natural variable, namely the modified torsional rigidity
of the superlevel sets.  This allows one to improve the cubic estimate
arising from the direct comparison of decreasing rearrangements.

We work at fixed torsional rigidity.  Let
\[
T(\Omega)=T(B_R)=:T_0
\]
and let \(u\) be the positive first Dirichlet eigenfunction of \(\Omega\),
normalized by
\[
\|u\|_{L^2(\Omega)}=1.
\]
We write
\[
\lambda:=\lambda_1(\Omega),
\qquad
\lambda_R:=\lambda_1(B_R),
\qquad
\delta_{\rm KJ}:=\frac{\lambda}{\lambda_R}-1.
\]

Let
\[
S:=T_{\rm mod}(\Omega;u)
\]
be the modified torsional rigidity associated with \(u\), in the sense
of \cite{BrascoKJ}, and let \(B_r\) be the ball such that
\[
T(B_r)=S.
\]
We set
\[
\lambda_r:=\lambda_1(B_r),
\qquad
b:=|B_r|,
\qquad
\bar t:=u^*(b).
\]
Thus
\[
|\{u>\bar t\}|=b.
\]

It will be useful to keep separate the two quantities
\[
a:=\frac{\lambda}{\lambda_r}-1,
\qquad
c:=\frac{\lambda_r}{\lambda_R}-1.
\]
Since
\[
\frac{\lambda}{\lambda_R}
=
\frac{\lambda}{\lambda_r}
\frac{\lambda_r}{\lambda_R},
\]
we have the exact identity
\begin{equation}\label{eq:split-KJ-deficit}
1+\delta_{\rm KJ}=(1+a)(1+c),
\qquad
\delta_{\rm KJ}=a+c+ac.
\end{equation}
In particular,
\[
0\leq a\leq\delta_{\rm KJ},
\qquad
0\leq c\leq\delta_{\rm KJ}.
\]
Moreover, since
\[
\frac{\lambda_r}{\lambda_R}
=
\left(\frac{R}{r}\right)^2,
\]
we also have
\begin{equation}\label{eq:r-deficit}
1-\frac rR\leq Cc.
\end{equation}

Let \(\widetilde u\) denote the Kohler--Jobin rearrangement of \(u\)
constructed in \cite[Proposition~4.1]{BrascoKJ}.  Thus
\(\widetilde u\in H^1_0(B_r)\) is radial and decreasing and
\begin{equation}\label{eq:KJ-energy-preservation}
\int_{B_r}|\nabla\widetilde u|^2
=
\int_\Omega|\nabla u|^2
=
\lambda,
\end{equation}
whereas, by the convex integral comparison,
\begin{equation}\label{eq:KJ-L2-increase}
A:=\int_{B_r}\widetilde u^2
\geq
\int_\Omega u^2=1.
\end{equation}
Since \(\widetilde u\) is an admissible function for
\(\lambda_1(B_r)\),
\[
\lambda_r
\leq
\frac{\lambda}{A}.
\]
Consequently,
\begin{equation}\label{eq:Aminus1}
0\leq A-1
\leq
\frac{\lambda}{\lambda_r}-1
=a.
\end{equation}

The following estimate is the key point.

\begin{proposition}\label{prop:tbar-KJ-improved}
There exist \(a_0>0\) and \(C>0\), depending only on \(n\) and on the
fixed torsional rigidity \(T_0\), such that, if \(a\leq a_0\), then
\begin{equation}\label{eq:tbar-square-A}
\bar t^2
\leq
C(A-1).
\end{equation}
In particular,
\begin{equation}\label{eq:tbar-square-a}
\bar t^2
\leq
Ca
\end{equation}
and therefore
\begin{equation}\label{eq:tbar-KJ-half}
\boxed{\;
\bar t\leq C\delta_{\rm KJ}^{1/2}.
\;}
\end{equation}
\end{proposition}

\begin{proof}
For \(t\in[0,\|u\|_\infty]\), set
\[
U_t:=\{u>t\},
\qquad
\mathcal T(t)
:=
T_{\rm mod}\bigl(U_t;(u-t)_+\bigr).
\]
Thus
\[
\mathcal T(0)=S.
\]
Following \cite[Section~4]{BrascoKJ}, let
\[
\phi:[0,S]\longrightarrow[0,\|u\|_\infty]
\]
be the inverse of \(\mathcal T\), so that
\[
\phi(S)=0,
\qquad
\phi(0)=\|u\|_\infty.
\]
We denote by
\[
\mu(t):=|\{u>t\}|
\]
the distribution function of \(u\).

Let \(\psi\) be the corresponding parametrization of the
Kohler--Jobin rearrangement \(\widetilde u\).  In the case \(p=2\),
equations (4.3)--(4.5) of \cite{BrascoKJ} show that the quantity
\[
m(\tau)
:=
-\phi'(\tau)\mu(\phi(\tau))
=
-\psi'(\tau)\mu_*(\psi(\tau))
\]
satisfies
\begin{equation}\label{eq:m-energy}
\int_0^S m(\tau)^2\,d\tau
=
\int_\Omega|\nabla u|^2\,dx
=
\lambda.
\end{equation}
Here \(\mu_*\) denotes the distribution function of \(\widetilde u\).

The particular advantage of the torsional parametrization is that
\(\mu_*(\psi(\tau))\) is explicit.  Since torsional rigidity scales as
\(r^{n+2}\), while volume scales as \(r^n\), we have
\begin{equation}\label{eq:model-distribution-torsion}
\mu_*(\psi(\tau))
=
b\left(\frac{\tau}{S}\right)^\alpha,
\qquad
\alpha:=\frac{n}{n+2}.
\end{equation}
Furthermore, equation (4.5) in \cite{BrascoKJ} gives
\[
-\psi'(\tau)
=
\frac{m(\tau)}{\mu_*(\psi(\tau))},
\qquad
-\phi'(\tau)
=
\frac{m(\tau)}{\mu(\phi(\tau))}.
\]
Since \(\psi(S)=\phi(S)=0\), it follows that
\begin{equation}\label{eq:psi-minus-phi}
\psi(\tau)-\phi(\tau)
=
\int_\tau^S
m(s)
\left(
\frac{1}{\mu_*(\psi(s))}
-
\frac{1}{\mu(\phi(s))}
\right)\,ds.
\end{equation}

We next rewrite the gain in the \(L^2\) norm produced by the
Kohler--Jobin rearrangement.  Using Cavalieri's principle in the
torsional variable and the identity defining \(m\), we obtain
\begin{align}
A-1
&=
\int_{B_r}\widetilde u^2\,dx
-
\int_\Omega u^2\,dx
\nonumber\\
&=
2\int_0^S
m(\tau)\bigl(\psi(\tau)-\phi(\tau)\bigr)\,d\tau.
\label{eq:L2-gain-torsion}
\end{align}

We now exploit the particular choice of \(\bar t\).  Let
\(\bar\tau\in[0,S]\) be such that
\[
\phi(\bar\tau)=\bar t.
\]
By definition,
\[
\mu(\phi(\bar\tau))=\mu(\bar t)=b.
\]
Since \(\phi\) is decreasing, for every
\(s\in[\bar\tau,S]\) we have
\[
\phi(s)\leq\bar t
\]
and consequently
\[
\mu(\phi(s))\geq b.
\]
On the other hand, by \eqref{eq:model-distribution-torsion},
\[
\mu_*(\psi(s))
=
b\left(\frac{s}{S}\right)^\alpha.
\]
Hence
\begin{align}
\frac{1}{\mu_*(\psi(s))}
-
\frac{1}{\mu(\phi(s))}
&\geq
\frac1b
\left[
\left(\frac{S}{s}\right)^\alpha-1
\right]
\nonumber\\
&\geq
\frac{\alpha}{bS}(S-s).
\label{eq:measure-gap-torsion}
\end{align}
The last inequality follows from
\[
x^{-\alpha}-1\geq\alpha(1-x),
\qquad 0<x\leq1.
\]

We also need a uniform upper bound for \(m\).
For almost every regular value \(t\), the formula for the modified
torsion in \cite[Proposition~3.5]{BrascoKJ} gives
\[
-\mathcal T'(t)
=
\frac{\mu(t)^2}
{\displaystyle\int_{\{u=t\}}|\nabla u|\,d\mathcal H^{n-1}}.
\]
Therefore, writing \(t=\phi(\tau)\),
\[
m(\tau)
=
\frac{\displaystyle
\int_{\{u=t\}}|\nabla u|\,d\mathcal H^{n-1}}
{\mu(t)}.
\]
Since \(u\) satisfies
\[
-\Delta u=\lambda u,
\]
integration over the superlevel set \(\{u>t\}\) gives
\[
\int_{\{u=t\}}|\nabla u|\,d\mathcal H^{n-1}
=
\lambda\int_{\{u>t\}}u\,dx.
\]
Consequently,
\begin{equation}\label{eq:m-upper}
m(\tau)
=
\lambda
\frac{\displaystyle\int_{\{u>t\}}u\,dx}
{\mu(t)}
\leq
\lambda\|u\|_{L^\infty(\Omega)}
\leq C.
\end{equation}
In the last inequality we used the standard domain-independent estimate
\[
\|u\|_{L^\infty(\Omega)}
\leq
C_n\lambda^{n/4}\|u\|_{L^2(\Omega)}
\]
and the fact that \(\lambda\) remains uniformly bounded when
\(\delta_{\rm KJ}\) is small.

We first prove the estimate for levels below a fixed small number
\(t_0>0\).  Let \(0<t\leq t_0\), and denote by \(\tau_t\) the number
such that
\[
\phi(\tau_t)=t.
\]
Assume also that \(t\leq\bar t\).  Then
\[
\mu(s)\geq b
\qquad\text{for }0\leq s\leq t.
\]
Using the change of variables \(s=\phi(\tau)\), we obtain
\begin{equation}\label{eq:K-low}
K_t
:=
\int_{\tau_t}^{S}m(\tau)\,d\tau
=
\int_0^t\mu(s)\,ds
\geq bt.
\end{equation}

Since \(m\leq C\), the elementary bathtub principle gives
\begin{equation}\label{eq:weighted-moment}
\int_{\tau_t}^{S}
m(s)(S-s)\,ds
\geq
cK_t^2
\geq
ct^2.
\end{equation}
Indeed, among all functions bounded by a fixed constant and with mass
\(K_t\), the left-hand side is minimized by concentrating the mass as
close as possible to \(S\).

Combining \eqref{eq:measure-gap-torsion} and
\eqref{eq:weighted-moment}, we obtain
\begin{equation}\label{eq:Jt}
J_t
:=
\int_{\tau_t}^{S}
m(s)
\left(
\frac{1}{\mu_*(\psi(s))}
-
\frac{1}{\mu(\phi(s))}
\right)\,ds
\geq
ct^2.
\end{equation}
By \eqref{eq:psi-minus-phi}, for every
\(\tau\in[0,\tau_t]\),
\[
\psi(\tau)-\phi(\tau)\geq J_t.
\]

It remains to show that
\[
\int_0^{\tau_t}m(\tau)\,d\tau
\]
is bounded from below.  Observe that
\begin{equation}\label{eq:upper-L1-u}
\int_\Omega u\,dx
\leq
\int_{B_r}\widetilde u\,dx
\leq
b^{1/2}A^{1/2}
\leq C,
\end{equation}
where the first inequality is the convex integral comparison of
\cite[Proposition~4.1 and Remark~4.3]{BrascoKJ}.
Thus
\[
\|\min\{u,t\}\|_{L^2}^2
\leq
t\int_\Omega u\,dx
\leq Ct.
\]
Choosing \(t_0>0\) sufficiently small, we infer
\[
\|(u-t)_+\|_{L^2}
\geq\frac12
\qquad
\text{for }0<t\leq t_0.
\]
Since \((u-t)_+\leq\|u\|_\infty\leq C\),
\[
\int_\Omega (u-t)_+\,dx
\geq c.
\]
On the other hand,
\[
\int_0^{\tau_t}m(\tau)\,d\tau
=
\int_t^{\|u\|_\infty}\mu(s)\,ds
=
\int_\Omega(u-t)_+\,dx.
\]
Therefore
\begin{equation}\label{eq:high-mass-lower}
\int_0^{\tau_t}m(\tau)\,d\tau
\geq c.
\end{equation}

Using \eqref{eq:L2-gain-torsion}, \eqref{eq:Jt} and
\eqref{eq:high-mass-lower}, we conclude that
\[
A-1
\geq
2J_t\int_0^{\tau_t}m(\tau)\,d\tau
\geq
ct^2
\]
for every
\[
0<t\leq\min\{\bar t,t_0\}.
\]
Taking
\[
t=\min\{\bar t,t_0\}
\]
gives
\begin{equation}\label{eq:min-tbar}
A-1
\geq
c\min\{\bar t,t_0\}^2.
\end{equation}
Since \(A-1\leq a\), if \(a\) is sufficiently small,
\eqref{eq:min-tbar} rules out the possibility
\(\bar t\geq t_0\).  Hence
\[
A-1\geq c\bar t^2,
\]
which proves \eqref{eq:tbar-square-A}.  Combining this with
\eqref{eq:Aminus1} gives
\[
\bar t^2\leq Ca.
\]
Finally \(a\leq\delta_{\rm KJ}\), and
\eqref{eq:tbar-KJ-half} follows.
\end{proof}

\begin{remark}
The important point is that the exponent \(1/2\) is not obtained by
improving the boundary behaviour of the radial eigenfunction.  Instead,
one avoids the boundary-strip argument altogether.

In the quantitative Chiti argument, a discrepancy of height
\(\bar t\) persists on an interval of length comparable with
\(\bar t\), and an \(L^2\) estimate therefore produces a contribution
of order \(\bar t^3\).  In the Kohler--Jobin setting the natural
quantity is instead the \(L^2\)-gain
\[
A-1
=
\|\widetilde u\|_2^2-\|u\|_2^2.
\]
Brasco's torsional parametrization expresses this gain as
\[
2\int_0^S m(\tau)(\psi-\phi)(\tau)\,d\tau.
\]
The explicit formula for the torsion of balls shows that the defect in
the reciprocal distribution functions vanishes linearly as
\(\tau\uparrow S\).  Since \(m\) is uniformly bounded for a normalized
eigenfunction, the resulting cost is quadratic in \(\bar t\), rather
than cubic.
\end{remark}

\begin{remark}
It is useful not to replace \(a\) and \(c\) immediately by the total
Kohler--Jobin deficit.  The estimates obtained above are
\[
\boxed{
\bar t^2\leq Ca,
\qquad
1-\frac rR\leq Cc,
\qquad
\delta_{\rm KJ}=a+c+ac.
}
\]
Thus the two sources of deficit are quantitatively different:
\(a\) measures the loss in the Kohler--Jobin rearrangement step,
whereas \(c\) measures the loss caused by replacing the full torsional
rigidity by the modified one.  Keeping these two quantities separate
may be important in the subsequent truncation argument.
\end{remark}

\begin{remark}
The argument above gives a genuine improvement from the cubic
mechanism to the square-root estimate
\[
\bar t\lesssim\delta_{\rm KJ}^{1/2}.
\]
It does not, by itself, give
\[
\bar t\lesssim\delta_{\rm KJ}.
\]
Obtaining the latter would require an additional estimate coupling the
two deficits \(a\) and \(c\), or a different estimate on the
low-level part of \(u\).  Such an estimate is not contained directly
in Proposition~4.1 of \cite{BrascoKJ}.
\end{remark}
```

The decisive step is Brasco's formula
\[
(-\psi')\mu_* =(-\phi')\mu
\]
together with the fact that, when the superlevel sets are parametrized through torsion,
\[
\mu_*(\psi(\tau))
=
|B_r|\left(\frac{\tau}{T_{\rm mod}}\right)^{n/(n+2)}.
\]
Brasco proves precisely these relations in the construction of the rearrangement and derives \(\psi\ge\phi\). [Cvgmt](https://cvgmt.sns.it/media/doc/paper/2083/KJp_rev.pdf)

This modification also changes the expected exponent in the remainder of the chain. From the truncation one still obtains
\[
\lambda_1(U_{\bar t})-\lambda_1(B_r)
\lesssim a+\bar t
\lesssim a^{1/2},
\]
so applying AKN, whose theorem controls **the square** of the resolvent distance by the Faber--Krahn deficit, naturally yields a distance of order \(a^{1/4}\), or a squared distance of order \(a^{1/2}\). [arXiv](https://arxiv.org/abs/2504.13053?utm_source=chatgpt.com)

The next point to attack is therefore very precise: determine whether, by using **together**
\[
a=\frac{\lambda(\Omega)}{\lambda(B_r)}-1
\quad\text{and}\quad
c=\frac{\lambda(B_r)}{\lambda(B_R)}-1,
\]
one can improve
\[
\bar t^2\lesssim a
\]
further, up to a linear estimate in the total deficit. This is exactly where one should avoid replacing \(a,c\leq\delta_{\rm KJ}\) prematurely.

