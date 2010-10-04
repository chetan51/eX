eX - A shorthand syntax for LaTeX
=================================

From the question I had posted on Stack Overflow:

> I love LaTeX. Let's get that straight right off the bat.
> 
> The only thing I'm wishing for is a clearer syntax that compiles into LaTeX, like Markdown for HTML. This is because most of the simple document creation that I do (like taking notes in class), could be faster and improved if I could just type 1/2 instead of \frac{1}{2} and it compiles it into a neat fraction. I know about and use AucTeX, and it makes for faster typing, but it's still not very clear and more prone to syntax errors in general.
> 
> If such a simpler syntax exists that compiles into LaTeX, please tell me in the answers below. If there is nothing satisfactory, I would love to start an open-source project towards this goal, but I would like to know of existing alternatives first.

The answers indicated that nothing satisfactory of the type exists yet, so eX is an attempt to make that goal a reality!

Let's start with a simple example
=================================

Instead of this:

	\documentclass[11pt]{article}
	\usepackage[margin=1in]{geometry}
	\usepackage{amsmath, amsthm, amssymb}

	\linespread{1.2}

	\renewcommand{\labelenumi}{\arabic{enumi}. }
	\renewcommand{\labelenumii}{\alph{enumii}.}

	\begin{document}
		\begin{flushright}
			\linespread{1}
			\small \normalsize
			Chetan Surpur \\
			CS161 \\
			HW 2 \\
			September 22, 2010
		\end{flushright}
		\begin{enumerate}
			\item
			  \begin{enumerate}
				\item
					Here is the quadratic formula.

					\begin{align*}
						\label{eq:quadratic-formula}
						x = \frac{{ - b \pm \sqrt {b^2 - 4a c} }}{{2 a}}
					\end{align*}
				\item
					In this example, $x$ is an inline variable and $x = \sum_{m = 0}^{\infty}{\sin{m}}$ is an inline equation.

					Oh, and here's a reference to the quadratic formula above \ref{eq:quadratic-formula}.

				\item
					Here is some plain text in a multi-line math equation.

					\begin{align*}
						n &= (5 * 2) - 3 \\
						&= 10 - 3 \\
						&= 7 \text{ chips left}
					\end{align*}

				\item
					eX does smart parentheses, which would normally be a pain in LaTeX.

					\begin{align*}
						r m = \left( \tan^{-1}{y/x} \right) m
					\end{align*}

				\item
					And to top it off, a bunch of greek letters in an integral.

					\begin{align*}
						\rho = \int_{2 \epsilon}^{5 \phi} \! \delta x \, \mathrm{d}x
					\end{align*}
					
			\item
			Let's look at how we would add formatted text and itemized lists.
			
			  \begin{itemize}
			    \item This text is \textbf{bold}.
			    \item This text is \emph{italicized}.
					\begin{itemize}
						\renewcommand{\labelitemi}{-}
						\item This is a sub list of the italicized text.
						\item Notice that it's easier to change the label with eX than LaTeX.
						\begin{enumerate}
							\item Let's start with number 1.
							\setcounter{enumi}{2}
							\item And then jump to number 3.
							\item It's easier with eX!
						\end{enumerate}
					\end{itemize}
			  \end{itemize}
		\end{enumerate}
	\end{document}

What if we could just write this:

	!homework:

	>> Chetan Surpur
	>> CS161
	>> HW 2
	>> September 22, 2010

	1. 	a. Here is the quadratic formula.
			
			-- quadratic formula
			x = (-b +- sqrt(b^2 - 4 a c))/(2 a)

		b. In this example, `x` is an inline variable and `x = sum_(m=0)^infinity(sin(m))` is an inline equation.

		   Oh, and here's a reference to the quadratic formula above {{quadratic formula}}.

		c. Here is some plain text in a multi-line math equation.
			
			n 	= (5 * 2) - 3
				= 10 - 3
				= 7 "chips left"

		d. eX does smart parentheses, which would normally be a pain in LaTeX.

			r m = tan^(-1)(y/x) m

		e. And to top it off, a bunch of greek letters in an integral.

			rho = int_(2 eps)^(5 phi)(delt x ,dx)

	       or even

		   	#r = int_(2 #e)^(5 #p)(#d x, dx)

	2. 	Let's look at how we would add formatted text and itemized lists.
	
		* This text is **bold**.
		* This text is __italicized__.
			- This is a sub list of the italicized text.
			- Notice that it's easier to change the label with eX than LaTeX.
				1. Let's start with number 1.
				3. And then jump to number 3.
				4. It's easier with eX!

** Wouldn't that be just dandy? **

I'd love to use eX for...
=========================

eX would be great for:

* Quick LaTeX document creation
* Taking notes in class or a meeting
* Doing a homework assignment
* Convincing your nerdy friend about some math theorem

In fact, you can quickly draft a good-looking document with it, and then make fine-tuned changes to the compiled LaTeX source. At any rate, it would be faster and more pleasant than cranking out raw LaTeX code.

Another major goal of this project is to make LaTeX available to the non-geeky masses. Math majors who just want to crank out equations on their computers can use eX and rejoice.

A quick note
============

eX is pronounced "ek", not "ex" (the same way LaTeX is pronounced "latek").
