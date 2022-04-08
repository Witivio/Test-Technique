# Witivio technical challenge

The objective of this challenge is to asses the candidate's knowledge and his capacity to adapt to different technologies.
This challenge will help us recognize the areas of improvement during the onboarding of the candidate.

# Completion time

1 day maximum.
The objective is to complete as many step as possible.

The candidate must notify tdechanterac@witivio.com when he begins to
work on the subject.

# Challenge subject

Antony Bearnett is a web developper specialized in .NET technologies and loves Angular.
He wants to renew his portfolio website. He has already thought about the layout and the theme he wants and has made a mock-up with photoshop.

The new website should look like this.

![new website - about page][aboutPage]

![new website - portfolio page][portfolioPage]

![new website - send message][sendMessageModal]

Antony updates regularly his LinkedIn profile with his information and skills and do not want to update his portfolio every time he updates his LinkedIn page.
He want to use the LinkedIn API to get its own information and display it into the website.

Also, all his old project pictures and information are already stored into an *Azure Blob Storage* and *Azure Cosmos Db*.

Finally he wants to have a button for head hunter to contact him.
This button would display a form where the head hunter could enter the informations about his company and the job they propose.

## Step 0 - Tools needed
- Visual Studio 2022 or Visual Studio Code
- The connection string to connect to the test databases will be send to you by email.

## Step 1 - Architecture
As Anthony is a .NET developper with a good knowledge of Angular he decide to start his new project with ASP.NET Core 6 and Angular embeded in it.
This will allow him to have his client and API in the same project.

![new website - architecture][architecture]

**Step completion goal:**
- Create a new ASP.NET Core 6 project with an angular app.

## Step 2 - Integrate the HTML template and initialize all Angular components.
To start his project Anthony bought an HTML and CSS template.
The HTML template is available [here](./html-template)

He decide to start working on the angular app.
His goal is to have the site's frame with dummy information

**Step completion goal:**
- Integrate the HTML & CSS template and the basic angular component architecture.

## Step 3 - Get the data from (our fake) LinkedIn Api and display it into the angular component
The swagger documentation of the (fake) LinkedIn api is available [here](https://witivio-technical-test-api.azurewebsites.net/swagger)
Antony already registered an API Key that will grant him access to its data.
This Api Key has to be added in an Api-Key header as described in the documentation
> witivio-test

**Important note:**
The (fake LinkedIn API) must be called from the ASP.NET Core server.

**Step completion goal:**
- Call the (fake) LinkedIn API through a HttpClient and expose it to the angular app through an API.

## Step 4 - Get the Image from blob storage and expose it through an API
Antony has already created the [Azure Blob Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction) as he's using it in other projects.
To access it, he uses the given Azure Storage connection string.

The images are stored in different folder depending to the type of projects
Container name : images
|__> photos
    |__> image1.png
    |__> image2.png
    |__> image3.png
    |__> image4.png
|__> project
    |__> image5.png
    |__> image6.png
    |__> image7.png
    |__> image8.png

![new website - folders][folders]

![new website - folders content][projectFolderContent]

![new website - folders content][pictureFoldersContent]

**Important note:**
The nuget package [Azure.Storage.Blobs](https://www.nuget.org/packages/Azure.Storage.Blobs) must be used to consume blobs.

**Step completion goal:**
- Create an API endpoint that exposes images from Azure Blob Storage.

 
## Step 5 - Get the images' related data and expose it through an API
Antony is currently storing his images metadata in a cosmos Db storage as he's using it in other projects.
To access it he uses the given Azure Cosmos Db connection string

**Important note:**
The nuget package [Microsoft.Azure.Cosmos](https://www.nuget.org/packages/Microsoft.Azure.Cosmos) must be used to consume the cosmosDb 

**Step completion goal:**
- Modify the existing API endpoint that exposes images and adds metadata retrieved from Azure Cosmos Db


# Q&A
Questions can be asked through email to tdechanterac@witivio.com


[aboutPage]: ./images/about.png
[portfolioPage]: ./images/portfolio.png
[sendMessageModal]: ./images/hire-me.png
[architecture]: ./images/architecture.png
[folders]: ./images/blobFolders.png
[projectFolderContent]: ./images/blobPicture1.png
[pictureFoldersContent]: ./images/blobPicture2.png