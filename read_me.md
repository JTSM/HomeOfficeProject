#Synopsis 

This project requires that I create a website with these listed qualities:

    1. Shows a list of applicants for a job. ✔
	2. Clicking a candidate’s name takes you to more information about that candidate, including their name, date of birth and a summary of their work experience. ✔
	3. Build an application using JavaScript, Java or Scala. ✔
	4. A readme that describes how to run it. ✔
	5. A design based upon Gov.uk frontend toolkit: "https://github.com/alphagov/govuk_frontend_toolkit". ✔
	6. Two clear tests. ✔
	7. Have the project emailed by the 2nd September 2016. ✔
	
#Additional Notes

	* The website has been designed with inspiration from the official Gov.uk website but is in no way a line-for-line clone of the said website.
    * The website has been configured to work on a variety of sized displays: phones / tablets / laptops and monitors. 
    * To view multiple screen functionality you can shrink and expand your internet browser window.
	* The website has been configured with a navigation bar icon for smaller displays. To see this, shrink your internet window to a small size.
    * This website has been tested with Google Chrome, Apple Safari, Monzilla Firefox, Internet Explorer 11 and Microsoft Edge. 
    * Font style and colours were selected from Gov.uk frontend toolkit as was the background colours and Home Office logo. 
	
#Getting Started

    * To get the project up and running download the zip file named HomeOfficeProject.zip located at: https://github.com/JTSM/HomeOfficeProject.git

#Prerequisites

	* Make sure you have a currently supported web browser installed such as Google Chrome: https://www.google.com/chrome/browser/desktop/index.html.
	* Make sure your browser (whichever you decide to use) is JavaScript compatible and that JavaScript is then enabled.
	* Make sure you have software installed on your device that enables you to unzip a compressed file such as 7-zip: http://www.7-zip.org/.
	* A live connection to the internet.

#Installing

	1. Task One: Make sure all the contents of the downloaded zip file is unzipped into its own seperate folder. 
	   This is an example: "c:\...\downloads\HomeOfficeProject".
    
    2. Make sure all these files are located in the unzipped folders: 
       HomeOfficeProject\css\stylesheet.css
                        \images\gov_uk_main_image.png 
                        \images\gov_uk_small_icon.png 
                        \images\ho_crest_13px_x2.png
                         candidate_page.html
                         read_me.md
                         
    3. To run website load *candidate_page.html* in your chosen web browser.

#Adding a Candidate to the Website

Locate this specific container:

```
<div class="container">
    <div class="panel-group">
        <div class="col-xs-0 col-md-3" style="background-color: #fff"></div>
        <div class="col-xs-12 col-md-6" style="background-color: #fff">
```
		
To add a candidate panel you input the following code at the bottom of the above third _<_/_div>_ section:

```
<div class="panel panel-default">
    <div class="panel-heading" class="text-center">
        <h4 class="panel-title">
            <a data-toggle="collapse" data-parent="#list-candidates" href="#candidate-?"><h4><strong>?</strong></h4></a>
        </h4>
    </div>
    <div id="candidate-?" class="panel-collapse collapse">
        <div class="panel body" style="padding-left: 5%; padding-right: 5%; padding-bottom: 2%" >
            <h4 style="color:#912B88"><strong>Full Name:</strong></h4>
            <p>?</p>
            <h4 style="color:#912B88"><strong>Date of Birth:</strong></h4>
            <p>DD/MM/YYYY</p>
            <h4 style="color:#912B88"><strong>Relevant Work Experience:</strong></h4>
            <li>Bulletpoint One.</li>
            <li>Bulletpoint Two.</li>
        </div>
    </div>
</div>
```
            
The second can either begin here or you can finish the container ending the last _</_div_>_ statements as shown below.

```
      </div>
    </div>
</div>
```

To complete the new candidate panel you must make sure "href="#candidate-?" and "id="candidate-?" contain the same number such as "candidate-thirteen". This is to enable smooth referencing between the two items. Make sure full-name includes any titles and middle-names. In "DD/MM/YYYY" enter numerical equivalent for days/months/years such as 21/05/1990. In relevant experience provide each bulletpoint with an opening _<_li_>_ and closing _</_li_>_.

#Test One: A Demonstration On How to Add a New Candidate to the Website

This is an example of how to add a new candidate to the website.

```
<div class="panel panel-default">
    <div class="panel-heading" class="text-center">
        <h4 class="panel-title">
            <a data-toggle="collapse" data-parent="#list-candidates" href="#candidate-thirteen"><h4><strong>Bradley White</strong></h4></a>
        </h4>
    </div>
    <div id="candidate-thirteen" class="panel-collapse collapse">
        <div class="panel body" style="padding-left: 5%; padding-right: 5%; padding-bottom: 2%" >
            <h4 style="color:#912B88"><strong>Full Name:</strong></h4>
            <p>Mr Bradley Paul White</p>
            <h4 style="color:#912B88"><strong>Date of Birth:</strong></h4>
            <p>22/11/1973</p>
            <h4 style="color:#912B88"><strong>Relevant Work Experience:</strong></h4>
            <li>**Gardener for 20 years.**</li>
            <li>**Takes part in fundraisers for the RSPCA**</li>
        </div>
    </div>
</div>
```

#Test Two: Syntax Success - Adding a Panel Correctly

A correctly added panel begins where the last _</_div_>_ statement of the previous panel ends. Common errors occur when the new panels are indented too far to the right in what is called a _child panel_ or too far to the left in what is called a _parent panel_.

```
            <li>"#"</li>
        </div>
    </div>
</div>
<div class="panel panel-default">
    <div class="panel-heading" class="text-center">
        <h4 class="panel-title">
            <a data-toggle="collapse" data-parent="#list-candidates" href="#candidate-"#""><h4><strong>"#"</strong></h4></a>
```

#Test Three: Common Syntax Errors - A Child Panel is Produced

A common mistake when adding a new candidate is producing a child panel. This is caused when the panel indentation is too far to the right of the last panels _</_div_>_ statement. This makes the newly added panel a subset of the above panel.

```
            <li>"#"</li>
        </div>
    </div>
</div>
    <div class="panel panel-default">
        <div class="panel-heading" class="text-center">
            <h4 class="panel-title">
                <a data-toggle="collapse" data-parent="#list-candidates" href="#candidate-"#""><h4><strong>"#"</strong></h4></a>
```

#Test Four: Common Syntax Errors - A Parent Panel is Produced

Another common mistake when adding a new candidate is producing a parent panel. This is caused when the panel indentation is too far to the left of the last panel _</_div_>_ statement. This makes the newly added panel a **parent panel**, a panel that is formatted differently to the above panel and other panels on the site.

```
               <li>"#"</li>
            </div>
        </div>
    </div>
<div class="panel panel-default">
    <div class="panel-heading" class="text-center">
        <h4 class="panel-title">
            <a data-toggle="collapse" data-parent="#list-candidates" href="#candidate-"#""><h4><strong>"#"</strong></h4></a>
```

##Built With

* **IDE Used:** Webstorm 2016
* **Languages Used:** JavaScript, Bootstrap, jQuery, HTML and CSS

## Version

* Version 1.0

## Author

* **James MacDonald** - *Built The Website* - https://www.github.com/jtsm


