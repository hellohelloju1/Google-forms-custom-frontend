# Google Forms custom front-end

tutorial for a custom front-end for collecting google forms responses

## example

<img src="/Screen Shot 2023-09-20 at 11.24.22 AM.png" alt="image" style="height: 200px;"/>

visit https://helptestingreplit.hellohelloju1.repl.co/ for a working demo

## tutorial
1. Create a google form, make sure its public

2. navigate to the three dots on the top right and click "get prefilled link"

<img src="/2.png" alt="image" style="height: 200px;"/>

3. Fill out the form, fill each field with the field name, then click get name

<img src="/3.png" alt="image" style="height: 200px;"/>

4. After you get the link, it should look something like

https://docs.google.com/forms/d/e/1FAIpQLSfzkq5HNXmg05A0q5UJY0tIeUaEWA-Z6DDWzfqJQJ2tvlSoIA/viewform?usp=pp_url&entry.2005620554=Name&entry.1045781291=Email@email.com&entry.1065046570=Address

we can see that in the URL, there are snippets that say something along the lines of "entry.2005620554=Name", the first part is the field id, and the second part is what question it belongs to, so we want to extract all of these ids.

Extract the following:

"1FAIpQLSfzkq5HNXmg05A0q5UJY0tIeUaEWA-Z6DDWzfqJQJ2tvlSoIA" - form id

"entry.2005620554" - field one id (name)

"entry.1045781291" - field two id (email)

"entry.1065046570" = field three id (address)

etc. 

5. you can now create a basic HTMl form with the extracted info

```text
      <form method="post" class="formm"id="form" action="https://docs.google.com/forms/u/0/d/e/[ENTER form id here]/formResponse">
    <label for="inp1">[any label you want]</label>
    <input class = "b" type="text" name="[field one id]" id="inp1"><br>
      <label for="inp1">Comment:</label>
    <input class="b" type="text" name="[field two id]" id="inp2"><br>
    <label for="inp1">Website:</label>
    <input class="b" type="text" name="[field three id]" id="inp3"><br>
    <input type="submit" value="Submit">
</form>
```
You can now style the form however you want.
for more fields, simply copy&paste the input field for every new field.
