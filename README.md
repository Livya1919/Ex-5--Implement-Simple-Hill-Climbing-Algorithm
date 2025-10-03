<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: LIVYA DHARSHINI G          </h3>
<h3>Register Number: 2305001013      </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

## PROGRAM
```python
import random
import string
def generate_random_solution(answer):
    l=len(answer)
    return [random.choice(string.printable) for _ in range(l)]
def evaluate(solution,answer):
    print(solution)
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        #to calculate the "difference" between two strings, character by character.
        #ord(s) - ord(t) calculates the difference between the ASCII values of the characters s and t.
         #abs() takes the absolute value of this difference to ensure that it is non-negative. This is important because the difference could be negative if s is less than t in terms of ASCII value.
         #The absolute value ensures that the difference is always positive or zero.
        diff += abs(ord(s) - ord(t))    return diff
def mutate_solution(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
def SimpleHillClimbing():
    answer="Artificial Intelligence"
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
       print("Score:", best_score, " Solution: ", "".join(best))  lsm
       if best_score == 0:
           break
       new_solution = mutate_solution(list(best))
       score = evaluate(new_solution, answer)
       if score < best_score:
           best = new_solution
           best_score = score
SimpleHillClimbing()
```

<hr>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
<img width="1292" height="472" alt="Screenshot 2025-10-03 084951" src="https://github.com/user-attachments/assets/55a6d319-e7f2-4af5-95f0-7667e4cbbca6" />

<img width="1283" height="467" alt="Screenshot 2025-10-03 085026" src="https://github.com/user-attachments/assets/5850cdea-a41b-459c-80d3-522f1c469101" />

<h2>Result:</h2>

Thus the program to implement Simple Hill Climbing Algorithm is executed successfully.
