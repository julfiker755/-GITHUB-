<p>
 <h1 style="color:red;" align="center">Git and Github 2023</h1>
</p>


### **গিটহাব কি ?**
GitHub সংস্করণ নিয়ন্ত্রণ এবং সহযোগিতার জন্য একটি ওয়েব-ভিত্তিক প্ল্যাটফর্ম যা গিট ব্যবহার করে, একটি বিতরণ করা সংস্করণ নিয়ন্ত্রণ ব্যবস্থা। এটি সফ্টওয়্যার কোড হোস্টিং এবং শেয়ার করার পাশাপাশি সফ্টওয়্যার প্রকল্প পরিচালনা এবং কোড বিকাশে অন্যদের সাথে সহযোগিতা করার জন্য একটি জনপ্রিয় প্ল্যাটফর্ম।
#


যদি  দুইটা  গিটহাব  একাউন্ট  থাকে  তাহলে  একটা  একাউন্ট  কিভাবে  উইন্ডোস ক্রেডিনশিয়াল থেকে  রিমোভ করতে হয় ?
![alt text](123.png)

2. গিটহাব  কিভাবে  নতুন  করে  ইমেইল  এবং  উজারনেম সেট  করতে  হয়  অনেকেই  উইন্ডস দিলে  এই  ঝেমেলায়  পরে 
 - git config --global user.name "John Doe"
 - git config --global user.email "johndoe@example.com"
 ![alt text](1234.png)

#
> ## **Fast time push**
- …or create a new repository on the command line
- echo "# simple" >> README.md
- git init
- git add .
- git commit -m "first commit"
- git branch -M main
- git remote add origin https://github.com/julfiker755/simple.git
- git push -u origin main
> ## **Second time** 
- git add .
- git commit -m "first commit"
- git push -u

> ## **Origin Https Change**
1. git remote remove origin
2. git remote add origin https://github.com/ProgrammingHero1/redux-cart.git
3. git push --set-upstream origin main
4. git push --set-upstream origin main -f
5. -------- Anathor system
6. git remote -v
7. git remote set-url origin https://github.com/ProgrammingHero1/redux-cart.git
8. git push

> ## **Origin diya download**
- git clone https://github.com/ProgrammingHero1/redux-cart.git

> ## github remove (.env node_modules) file
0. ভুলে .env ফোল্ডারটি git add,commit push করে  গিটহাব  আপলোড করে ফেলেছি.এখন কি করব ✔Solutions
1. git rm -r --cached .env
2. git add .
3. git commit -m "removeing .env file"
4. git push -f
0. ভুলে node_modules ফোল্ডারটি git add,commit push করে  গিটহাব  আপলোড করে ফেলেছি.এখন কি করব ✔Solutions
1. git rm -r --cached node_modules
2. git add .
3. git commit -m "removeing node_modules"
4. git push -f


> ## Markdown
- Readme file ta dekte caile…………….
- clt+shift+P and Markdown:Open Preview(clt+Shit+V)
- Markdown main Wepsite link:-*[Markdown Cheat Sheet link](https://www.markdownguide.org/cheat-sheet/#overview)*
> ## Git Branch Commands
| Command | Description |
| ----------- | ------------ |
| git branch | List branches (the asterisk denotes the current branch) |
| git branch [branch name] | Create a new branch |
| git branch -d [branch name]| Delete a branch |
| git branch [branch name] | Create a new branch |
| git checkout -b [branch name] | Create a new branch and switch to it |
| git checkout - | Switch to the branch last checked out |
| git checkout [branch name] | Switch to a branch |
|
---> Git Branch Commands Wepsite link:-*[Git Branch Com](https://github.com/joshnh/Git-Commands)*
> ## What is Gitignore
- কোন ফাইলকে গিটহাবে পাঠাতে না  চাইলে আমরা .gitignore  ব্যবহার করি
![alt text](12345.png)
> ## Visual Studio Code Extension
- Visual Studio Code extension
  - Live Server
  - css-auto-prefix
  - Monokai Dark Soda(color change)/Flatland Monokai Theme
  - Material Icon Theme/Theme - Seti-Monokai
  - Code Spell Checker(English check banna vull)
  - Better Comments
  - Beautify (alo melo code format kore)
- API check
  - postman
  - Thunder Client
  - RapidAPI Client
- react js extension
  - Reactjs code snippets-(rsc,rfc)
  - react emmet{settings->extensition->Include Languages}=add korte hobe
  - Auto Import
  - Redux DevTools
  - React Extension Pack
  - Axios Snippets
  - html to jsx
- tawild css extenstion
  - Tailwind CSS IntelliSense
  - Inline fold
- react js one file extension
  - React Extension Pack
  - React Extensions Pack
 ![alt text](11.png)
> ## Brower Extensition
- Brower Extension most important
  - Copyfish [note:selct kore copy koro]
  - GoFullPage [note:full page pdf,jpg,png kora]
  - Pesticide for Chrome [note:website ke select kora]
  - React Developer Tools  [note:react most popular extensition]
  - Redux DevTools  [note:Redux Dev tools]
  - JSON Formatter [scrial show data]
  - JSON Viewer [scrial show data the my best]
  - Temp Mail [Random email ganared]
  - driver booster [windows driver+(Not a extensiton pack)]
  
>  ## Github Profile design demo link
 - [Streak Stats](https://github-readme-streak-stats.herokuapp.com/demo/?fbclid=IwAR3ii_ruZb77CXCzR0zuZH1KszltxtoVgW-K9YPcfc4YXeCZycEuQ6-58Co)  ||  [Average](https://github.com/avgupta456/github-trends?fbclid=IwAR2uJF-QjJW5ugP4hBxlYjAn4yL70NqRd672HvgeGArk5XqkHVhHXeiBy5o)  ||  [Skill icons](https://github.com/tandpfun/skill-icons?fbclid=IwAR0Ht-cpZP6RGrmF2Jwf2TsNn-eFdm6MsnMcsrD7qqdm-KEs-fxAwIbZxHM)  || [Profile Summary](https://github.com/vn7n24fzkq/github-profile-summary-cards?fbclid=IwAR3faUdbfeii6_X2ZWbP0f5Hn2UEQxQE_e0WhNZscpCRS2-0iYC40_JmOKc)  || [Profile Trophy](https://github.com/ryo-ma/github-profile-trophy) || [github-readme-streak-stats](https://github.com/DenverCoder1/github-readme-streak-stats/blob/main/docs/themes.md) || [github-readme-stats](https://github.com/anuraghazra/github-readme-stats?tab=readme-ov-file)
|| [social icon](https://github.com/alexandresanlim/Badges4-README.md-Profile?tab=readme-ov-file#-social-)
 

> Javascript Books All Resources:: [Book](https://with.zonayed.me).

> Responsive check [Responsive](https://ui.dev/amiresponsive).

> Doller check  website [Dooler](https://www.taptapsend.com/?dl=1).

> website color check [website-magazine](https://huemint.com/website-magazine/).


