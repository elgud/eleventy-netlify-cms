---
layout: layouts/childpage.njk
title: Pseudocode
templateClass: tmpl-home
eleventyNavigation:
  key: Pseudocode
  parent: Javascript
  order: 4
---

<div class="container mt-4">
    <h1>Pseudocode Tasks</h1>

<code><pre>
    LOOP through numbers 0-100
        IF the number is a multiple of 3 and 5
            THEN output "fizzbuzz"
        ELSE IF number is a multiple of 3
            THEN output "fizz"
        ELSE IF the number is a multiple of 5
            THEN output "buzz"
        ELSE
            THEN output number
</pre></code>

<h2>Have I read this book?</h2>
<p>Supposed to follow spec exactly. But I didn't want to!</p>
<pre>
arrBooks= [
    {
        title:'The Lord of the Rings'
        author: 'J R R Tolkien',
        blnRead: false
    },
    title:'Harry Potter and the Philosopher's Stone'
        author: 'J K Rowling',
        blnRead: true
    }
]

    VARIABLES
        booksRead  (list)
        booksToRead  (list)

    FUNCTION have-I-read({book})
        SET {found} to false
        LOOP through each book in {booksRead}
            IF (title of current book is the same as {book} title) AND (author of current book is the same as author of {book})
                THEN OUTPUT You have read {book}
                    SET {found} to true
                    STOP Looping
        IF NOT {found}
            OUTPUT You have not read {title} by {author}, do you want me to add the book to {BooksToRead}?
            
</pre>

<h2>fixStart(word)<h2>
<pre>
FUNCTION fixStart(word):
    SET {firstLetter} to first letter of word
    LOOP through rest of letters of word
        IF letter is the same as {firstLetter}
            THEN REPLACE letter with *
    OUTPUT changed word
</pre>

</div>

<script>
  //LOOP through numbers 0-100
  for (counter=1; counter<=100; counter++){
        var message = '';
        //IF number is a multiple of 3
        if(counter % 3 == 0){
            //THEN output "fizz"
            message +='fizz';
        }
        //IF the number is a multiple of 5
        if (counter % 5 == 0){
            //THEN output "buzz"
            message += 'buzz';
        }
        //IF message isn't set output the counter
        if (!message){
            // Then output counter
            message=counter;
        } 
        console.log(message);
    }
</script>  