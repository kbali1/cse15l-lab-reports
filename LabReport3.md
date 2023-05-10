#### Kirsten Bali

## Lab Report 3: Researching Commands

# Grep

### 1. grep -i string filename
https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/ [https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/]

This grep command line is case insensitive and searches for strings that match the string. It then returns the lines in the file the string is in. If you want to find the lines that contain a word that is capitalized or not, then use `grep -i`.

    $ grep "THAT" pmed.0020281.txt
    
    $ grep -i "THAT" pmed.0020281.txt
        PLoS Medicine —that involves the pharmaceutical industry, pharmaceutical
        forces that zealously guard their secrets could not have been told without the help of
        courageous men and women [1, 2] For that reason, those of us who congregated in Washington,
        misrepresented pharmaceuticals; clinical research trial results that have been sequestered
        pharmaceuticals that are detailed to physicians, not to save lives or necessarily improve
        is to tell the truth. That honest effort is the source of any ethical difference we can or
        might make. Truth is the basis for the power of a whistleblower, one that can withstand the
        assault of unprecedented odds against being heard put forth by that sum of political power,
        
When I used the grep command and typed "THAT" without the `-i` option, it did not return anything because the grep command alone is case sensistive. However, when I used `-i`, with "THAT", the terminal printed out all the lines with the string "that".
  
  
    $ grep "The" pmed.0020281.txt
        Whistleblowers serve no function if they cannot tell their stories. The present story of
        A whistleblower's success depends upon competent and articulate media. The debate to
        
    $ grep -i "The" pmed.0020281.txt
        Whistleblowers serve no function if they cannot tell their stories. The present story of
        PLoS Medicine —that involves the pharmaceutical industry, pharmaceutical
        benefit management corporations, the managed care industry, and the political and lobbying
        forces that zealously guard their secrets could not have been told without the help of
        D.C., on May 15th, 2005, at the invitation and support of the Public Library of Science and
        the Government Accountability Project feel particularly humbled and grateful to these two
        sponsors. Our convictions could not have been aired were it not for the essential First
        Amendment work of responsible journalists, who exemplify the best in investigatory
        For me, whistleblowing is not a theoretical exercise. It has a human face and tangible
        features. It is the face of children and adults who have been injured or killed by
        from the scientific community and whose incomplete findings cause injury; and
        the health or welfare of the recipients, but to make money.
        In the lonely and, at times, discouraging world of whistleblowing, we whistleblowers are
        passionate, and often successful, because our efforts have a different goal than the
        is to tell the truth. That honest effort is the source of any ethical difference we can or
        might make. Truth is the basis for the power of a whistleblower, one that can withstand the
        A whistleblower's success depends upon competent and articulate media. The debate to
        improve the status quo—be it in pharmaceutical marketing or managed-care decision
        success (I have adapted his comments for all of us who gathered in Washington in mid-May
        2005): “To leave the world a bit better, whether by a healthy child, a garden patch or a
        redeemed social condition; to know even one life breathed easier because you have lived;

The first example without the use of `-i` returns all lines with "The" and not "the". The second command line with `-i` returns not only lines with "The" but lines with "the" as well.



### 2. grep -c string filename
https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/ [https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/]

The command line `grep -c` counts how many lines have the string in the file. If you want to find how many lines in a text contain a certain word, then use the `grep -c` command option.

    $ grep -c "increased" rr74.txt
      28


The line above counts how many times the string "increased" appear in a line and counts those lines. It then returns the count. It doesn't matter if the string is "increased" or "increasedly". As long as the string has the word "increased" in it, it counts that line.

    $ grep -c "the" rr74.txt
      102
  
The command above counts how many times "the" apears in the text file. It also counts the the lines with the string "there" or any other word that contains the string "the".



### 3. grep -v string filename
https://www.geeksforgeeks.org/grep-command-in-unixlinux/ [https://www.geeksforgeeks.org/grep-command-in-unixlinux/]

The command line `grep -v` returns lines that do not contain the string. Use `grep v` when you want to find lines that do not contain a certain character or string.

    $ grep -v "the" working_for_Free.txt
        Working for Free Pays Off for Caring Lawyer
        Bruce Zucker chooses to provide pro bono legal aid to poor
        tenants over more prestigious work, and it has become his life's
        passion.
        Karima A. Haynes
        Sunday, January 5, 2003
        Nothing in Bruce Zucker's upbringing seems to have prepared him
        A tall, athletic man who favors pleated khakis and starched
        button-down shirts, Zucker grew up in an upper-middle-class enclave
        every day.
        "There was no big, dramatic event in my childhood that made me
        want to help poor people," Zucker said. "But it doesn't take a
        thing."
        ...
        The State Bar of California presented Zucker with its 2002
        President's Pro Bono Service Award for his volunteer work with
        tenants' rights issues. The award was established in 1983 to give
        statewide recognition to attorneys for providing pro bono legal
        County Superior Court, where he has served as a temporary judge in
        Small Claims Court and has volunteered with a court-sponsored
        program for at-risk high school students.

In the example above, there are no lines that contain the string "the" in it except for "There" and "The" because the grep command is case sensitive. 


    $ grep -v "a" working_for_Free.txt
        for his life's work defending the poor.
        right.
        thing."
        problems.
        Internet.
        services to the poor.
        seriously."
        He's willing to help."
        he gets worn down by his clients' overwhelming poverty. To relieve
        professor.
  
The example above does not return any line with strings that have the letter "a" in it. 


### 4. grep -w string filename
https://www.geeksforgeeks.org/grep-command-in-unixlinux/[https://www.geeksforgeeks.org/grep-command-in-unixlinux/]

The `-w` option return lines that contain the string alone and not lines with the string in other strings. The command line `grep -w` helps find words by itself and not words that contain the word you want to find.

    $ grep "a" preface.txt
            We present the narrative of this report and the recommendations that flow from it to
                the President of the United States, the United States Congress, and the American
                people for their consideration. Ten Commissioners-five Republicans and five
                Democrats chosen by elected leaders from our nation's capital at a time of great
                partisan division-have come together to present this report without dissent.
            We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                the United States. The nation was unprepared. How did this happen, and how can we
                avoid such tragedy again?
                ... 
               
    $ grep -w "a" preface.txt
                Democrats chosen by elected leaders from our nation's capital at a time of great
                We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                sharing information across a large and unwieldy government that had been built in a
                together as a nation. The test before us is to sustain that unity of purpose and
                meet the challenges now confronting us. We need to design a balanced strategy for
                have searched records and produced a multitude of documents for us. We thank
                assistance. We owe a huge debt to their investigative labors, painstaking attention
                This final report is only a summary of what we have done, citing only a fraction of
                inevitably will come to light. We present this report as a foundation for a better
                understanding of a landmark in the history of our nation.
                We also approach the task of recommendations with humility. We have made a limited  
                
Grep without `-w` returns lines that have strings with the string "a" in it as well as the string "a" by itself. Grep with `-w` return lines that have the string "a" by itself and not lines that also have "a" in the strings.


    $ grep "con" preface.txt
                people for their consideration. Ten Commissioners-five Republicans and five
                and border control, the flow of assets to terrorist organizations, commercial
                aviation, the role of congressional oversight and resource allocation, and other
                targets. Collateral damage is not in its lexicon.
                different era to confront different dangers.
                meet the challenges now confronting us. We need to design a balanced strategy for
                dialogue. We want to express our considerable respect for the intellect and judgment
                Philip Zelikow, has contributed innumerable hours to the completion of this report,
                setting aside other important endeavors to take on this all-consuming assignment.
                They have conducted the exacting investigative work upon which the Commission has
            We conclude this list of thanks by coming full circle: We thank the families of 9/11,
                the sources we have consulted. But in an event of this scale, touching so many
                issues and organizations, we are conscious of our limits. We have not interviewed
                number of them. We decided consciously to focus on recommendations we believe to be
                considered the views of others. We hope our report will encourage our fellow
                
     $ grep -w "con" preface.txt
  
Grep without `-w` returns lines that have strings that contain the string "con". But grep with `-w` does not return any lines that have string "con" by itself. Because "con" is a nonexistent word in the text.
