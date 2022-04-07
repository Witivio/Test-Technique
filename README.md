# Witivio technical subject

The objective of this subject is to take stock of the candidate's knowledge in order to best support him during the integration of Witivio and the increase in skills on the virtual agent studio solution.

# Completion time

1 day maximum.
The objective is to complete as much step as possible.

The candidate must notify tdechanterac\@witivio.com when he begins to
work on the subject.

# Subject

Antony Bearnett is a web developper specialized .NET technologies and really likes Angular.
He want to renew his Portfolio website.
He already though about the layout and the theme he want and has made a mock-up with photoshop.

The new website should look like this.

![new website - about page][aboutPage]

![new website - portfolio page][portfolioPage]

![new website - send message][sendMessageModal]

Antony update regularly he linkedin profile with his informations and skill and do not want to update his portfolio every time he update his linkedin page.
He has the idea to use the Linkedin API to get its own informations and display it into the website.

Also, all his old project pictures and informations are already stored into an Azure Blob Storage and Azure Cosmos Db.

Finally he want to have a button for recrutor to contact him.
This button would display a form where the recruitor could enter the informations about his company and the job they propose.

## Step 0 - Tools needed - 
- Visual Studio 2022 or Visual Studio Code
- The connection string to connect to the test databases will be send to you by email.

## Step 1 - Architecture
As Anthony is a .NET developper with a good knowledge of Angular he decide to start his new project with an ASP NET Core 6 project with Angular embeded in it.
This will allow him to have his client and API in the same project.

![new website - architecture][architecture]

**Step completion goal :**
- Create a new ASP NET Core 6 project with an angular app.

## Step 2 - Integrate the HTML template and initialize all Angular components.
To start his project Anthony bought an HTML and CSS template.
The HTML template is available [here](./html-template)

He decide to start working on the angular app.
His goal is to have the skeleton of the site with dummy informations

**Step completion goal :**
- Integrate the HTML & CSS template and the basic angular component architecture.

## Step 3 - Get the data from (our fake) Linkedin Api and display it into the angular component
The swagger documentation of the (fake) linkedin api is available [here](https://witivio-technical-test-api.azurewebsites.net/swagger)
Antony already registered an API Key that will grant him access to its data.
This Api Key has to be added in an Api-Key header as described in the documentation
> witivio-test

**Important note :**
The (fake linkedin API) must be called from the ASP NET Core server

**Step completion goal :**
- Consumme the (fake) linkedin API through a HttpClient and expose it to the angular app through an API.

## Step 4 - Get the Image from blob storage and expose it through an API
Antony already created the [Azure blob storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction) as he's using it in other projects.
To access it he uses the given Azure Storage connection string

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

**Important note :**
The nuget package [Azure.Storage.Blobs](https://www.nuget.org/packages/Azure.Storage.Blobs) must be used to consume blobs

**Step completion goal :**
- Create an API endpoint that expose images from Azure Blob storage

 
## Step 5 - Get the images' related data and expose it trough an API
Antony is currently storing his images metadata in a cosmos Db storage  as he's using it in other projects.
To access it he uses the given Azure Cosmos Db connection string

**Important note :**
The nuget package [Microsoft.Azure.Cosmos](https://www.nuget.org/packages/Microsoft.Azure.Cosmos) must be used to consume the cosmosDb 

**Step completion goal :**
- Modify the existing API endpoint that expose images and add metadata retrieve from Azure Cosmos Db


# Q&A
Questions can be asked through email to tdechanterac@witivio.com

[aboutPage]: ./images/about.png
[portfolioPage]: ./images/portfolio.png
[sendMessageModal]: ./images/hire-me.png
[architecture]: ./images/architecture.png
[folders]: ./images/blobFolders.png
[projectFolderContent]: ./images/blobPicture1.png
[pictureFoldersContent]: ./images/blobPicture2.png