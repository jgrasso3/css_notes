HTML

h1 - 6

p

<img src="images/pasta.png" alt="fresh pasta dough">

<ul> || <ol>
  <li><strong>TIME:</strong> About 45min</li>
  <li><strong>Rating:</strong> 5</li>
  <li><strong>Notes</strong> <a href="#communityNotes">Read community notes</a></li>
</ul>

Forms

  <form action="/subjects" method="get">
    Text Input
    <div>
      <label for="title">Course Title</label>
      <input type="text" id="title" name="courseTitle" required>
    </div>

    Text Area
    <div>
      <label for="desc">Course Description</label>
      <div>
        <textarea name="desc" id="desc" cols="30" rows="10"></textarea>
      </div>
    </div>

    Select Box
    <div>
      <label for="skill">Skill Level</label>
      <select name="skill" id="skill">
        <option value="1">Beginner</option>
        <option value="2">Intermediate</option>
        <option value="3">Expert</option>
        <option value="4">All</option>
      </select>
    </div>

    Checkbox
    <div>
      <label for="ready">Ready to publish course?</label>
      <input type="checkbox" id="ready" name="publish">
    </div>

    <div>
      <button>Submit</button>
    </div>
  </form>