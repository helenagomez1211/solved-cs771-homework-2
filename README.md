Download Link: https://assignmentchef.com/product/solved-cs771-homework-2
<br>
Intro to Machine Learning

<strong>Instructions:</strong>

<ul>

 <li>Only electronic submissions will be accepted. Your main PDF writeup must be typeset in LaTeX (please also refer to the “Additional Instructions” below).</li>

 <li>The PDF writeup containing your solution has to be submitted via Gradescope https://www.gradescope. com/ and the code for the programming part (to be submitted via this Dropbox link: https://</li>

</ul>

<a href="https://tinyurl.com/cs771-a20-hw2)">tinyurl.com/cs771-a20-hw2</a><u>)</u>

<ul>

 <li>We have created your Gradescope account (you should have received the notification). Please use yourIITK CC ID (not any other email ID) to login. Use the “Forgot Password” option to set your password.</li>

</ul>

<strong>Additional Instructions</strong>

<ul>

 <li>We have provided a LaTeX template file tex to help typeset your PDF writeup. There is also a style file ml.sty that contain shortcuts to many of the useful LaTeX commends for doing things such as boldfaced/calligraphic fonts for letters, various mathematical/greek symbols, etc., and others. Use of these shortcuts is recommended (but not necessary).</li>

 <li>Your answer to every question should begin on a new page. The provided template is designed to do this However, if it fails to do so, use the clearpage option in LaTeX before starting the answer to a new question, to <em>enforce </em>this.</li>

 <li>While submitting your assignment on the Gradescope website, you will have to specify on which page(s) is question 1 answered, on which page(s) is question 2 answered etc. To do this properly, first ensure that the answer to each question starts on a different page.</li>

 <li>Be careful to flush all your floats (figures, tables) corresponding to question n before starting the answer to question n + 1 otherwise, while grading, we might miss your important parts of your answers.</li>

 <li>Your solutions must appear in proper order in the PDF file i.e. solution to question n must be complete in the PDF file (including all plots, tables, proofs etc) before you present a solution to question n + 1.</li>

 <li>For the programming part, all the code and README should be zipped together and submitted as a single file named zip. Please DO NOT submit the data provided.</li>

</ul>




<strong>Problem 1 (20 marks)</strong>

<strong>(Second-Order Optimization for Logistic Regression)</strong> Show that, for the logistic regression model (assum­ing each label y<sub>n</sub> ∈ {0, 1}, and no regularization) with loss function L(w) = − &gt;N <sub>n</sub>=1(ynw<sup>T</sup>xn − log(1 + exp(wTx<sub>n</sub>))), iteration t of a<em> second-order</em> optimization based update<sub> w</sub>(t+<sup>1</sup>) =<sub> w</sub>(t) − H(t)_1g(t), where H denotes the Hessian and g denotes the gradient, reduces to solving an<em> importance-weighted</em> regression problem of the form<sub> w</sub>(t+<sup>1</sup>) = arg min &gt;Nn=1 γ(t)

n (ˆy<sup>(t)</sup>

n − w<sup>T</sup>x<sub>n</sub>)<sup>2</sup>, where γ<sub>n</sub> denotes the importance of the n<sup>th</sup> train­ing example and ˆy<sub>n</sub> denotes a modified real-valued label. Also, clearly write down the expression for both, and provide a brief justification as to why the expression of γ<sub>n</sub> makes intuitive sense here.

<strong>Problem 2 (20 marks)</strong>

<strong>(Perceptron with Kernels)</strong> We have seen that, due to the form of Perceptron updates w = w + ynxn (ignore the bias b), the weight vector learned by Perceptron can be written as w =EN n=1 αnynxn, where α<sub>n</sub> is the number of times Perceptron makes a mistake on example n. Suppose our goal is to make Perceptron learn nonlinear boundaries, using a kernel k with feature map φ. Modify the standard Perceptron algorithm to do this. In particular, for this kernelized variant of the Perceptron algorithm (1) Give the initialization, (2) Give the mistake condition, and (3) Give the update equation.

<strong>Problem 3 (20 marks)</strong>

<strong>(SVM with Unequal Class Importance)</strong> Sometimes it costs us a lot more to classify negative points as positive than positive points as negative. (for instance, if we are predicting if someone has cancer then we would rather err on the side of caution (predicting “yes” when the answer is “no”) than vice versa). One way of expressing this in the support vector machine model is to assign different costs to the two kinds of mis-classification. The primal formulation of this is:

<table>

 <tbody>

  <tr>

   <td width="279">min,b,<strong>ξ</strong></td>

   <td width="57"><u>|</u><u>||w|</u><u><sup>2</sup></u>+2</td>

   <td width="24">~Nn=1</td>

   <td width="287">Cy<sub>n</sub>ξn</td>

  </tr>

 </tbody>

</table>




subject to y<sub>n</sub>(w<sup>T</sup>x<sub>n</sub> + b) ≥ 1 − ξ<sub>n</sub>and ξ<sub>n</sub> ≥ 0, ∀n.

The only difference is that instead of one cost parameter C, there are two, C+1 and C<em>_</em>1, representing the costs of misclassifying positive examples and misclassifying negative examples, respectively.

Write down the Lagrangian problem of this modified SVM. Take derivatives w.r.t. the primal variables and construct the dual, namely, the maximization problem that depends only on the dual variables α, rather than the primal variables. In your final PDF write-up, you need not give each of every step in these derivations (e.g., standard steps of substituting and eliminating some variables) but do write down the key steps. Explain (intuitively) how this differs from the standard SVM dual problem; in particular, how the C variables differ between the two duals.

<strong>Problem 4 (20 marks)</strong>

<strong>(SGD for</strong> K<strong>-means Objective)</strong> Recall the K-means objective function: L =~N ~K k=1 znk||xn − µk||<sup>2</sup>.

n=1

As we have seen, the K- means algorithm minimizes this objective by taking a greedy iterative approach of assigning each point to its closest center (finding the z<sub>n</sub>k’s) and updating the cluster means {µk}Kk=1. The standard K-means algorithm is a batch algorithm and uses all the data in every iteration. It however can be made online by taking a random example x<sub>n</sub> at a time, and then (1) assigning x<sub>n</sub> “greedily” to the “best” cluster, and (2) updating the cluster means using SGD on the objective L. Assuming you have initialized {µk}Kk=1 randomly and are reading one data point x<sub>n</sub> at a time,

<ul>

 <li>How would you solve step 1?</li>

 <li>What will be the SGD-based cluster mean update equations for step 2? Intuitively, why does the update equation make sense?</li>

</ul>




<ul>

 <li>Note that the SGD update requires a step size. For your derived SGD update, suggest a good choice of the step size (and mention why you think it is a good choice).</li>

</ul>

<strong>Problem 5 (20 marks)</strong>

<strong>(Kernel </strong>K<strong>-means) </strong>Assuming a kernel k with an infinite dimensional feature map φ (e.g., an RBF kernel), we can neither store the kernel-induced feature map representation of the data points nor can store the cluster means in the kernel-induced feature space. How can we still implement the kernel K-means algorithm in practice? Justify your answer by sketching the algorithm, showing all the steps (initialization, cluster assignment, mean computation), clearly giving the mathematical operations in each. In particular, what is the difference between how the clusters means would need to be stored in kernel K-means versus how they are stored in standard K-means? Finally, assuming each input to be D-dimensional in the original feature space, and N to be the number of inputs, how does kernel K-means compare with standard K-means in terms of the cost of input to cluster mean distance calculation (please answer this using the big O notation)?

<strong>Problem 6 (Programming Problem, 50 marks)</strong>

<strong>Part 1: </strong>You are provided a dataset in the file binclass.txt. In this file, the first two numbers on each line denote the two features of the input x , and the third number is the binary label y<sub>n</sub> E {−1, +1}.

Implement a generative classification model for this data assuming Gaussian class-conditional distributions of the positive and negative class examples to be N(x|µ+, a2 +I2) and N(x|µ_, a2 _I2), respectively. Note that here I2 denotes a 2 x 2 identity matrix. Assume the class-marginal to be p(y = 1) = 0.5, and use MLE estimates for the unknown parameters. Your implementation need not be specific to two-dimensional inputs and it should be almost equally easy to implement it such that it works for any number of features (but it is okay if your implementation is specific to two-dimensional inputs only).

On a two-dimensional plane, plot the examples from both the classes (use red color for positives and blue color for negatives) and the <strong>learned decision boundary </strong>for this model. Note that we are not providing any separate test data. Your task is only to learn the decision boundary using the provided training data and visualize it.

Next, repeat the same exercise but assuming the Gaussian class-conditional distributions of the positive and negative class examples to be N(x|µ+, a<sup>2</sup>I2) and N(x|µ_, a<sup>2</sup>I2), respectively.

Finally, try out an SVM classifier (with <strong>linear kernel</strong>) on this data (we’ve also provided the data in the format libSVM requires) and show the learn decision boundary. For this part, you do not need to implement SVM. There are many nice implementations of SVM available, such as the one in scikit-learn and the very popular libSVM toolkit. Assume the “C” (or A) hyperparameter of SVM in these implementations to be 1.

<strong>Part 2: </strong>Repeat the same experiments as you did for part 1 but now using a different dataset binclassv2.txt. Looking at the results of both the parts, which of the two models (generative classification with Gaussian class-conditional and SVM) do you think seems to work better for each of these datasets, and in general?


