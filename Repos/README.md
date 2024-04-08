# Repository Organization

In their quest to be minimalist GitHub has never had the concept of creating groups or folders for repositories. This can make it difficult to organize repositories, especially when you have a lot of them. Fear not, there are some features that can leverage to get a similar effect.

## Repository Topics

GitHub allows you to add topics to your repositories. These topics can be used to group repositories together. For example, you could add the topic `python` to all your Python repositories, and the topic `javascript` to all your JavaScript repositories. This way you can easily filter your repositories by language.

### Reasons why topics might not be enough
- Topics were primarily designed to allow people to better discover open source projects. They are not meant to be used as a way to organize private repositories.
- When you click a topic, you are taken to a page that lists all public repositories with that topic. This is not the desired behavior when you are trying to organize your private repositories.

## Repository properties

> [!NOTE]  
> This feature is only available for GitHub Enterprise Cloud and GitHub Enterprise Server.

Recently in 2023 GitHub introduced a new feature that allows you to add properties to your repositories. Properties can be required or optional and either text or multiple choice. This makes it easy to filter all repositories with a specific property, or even a combination of properties.

### Reasons why properties might not be enough
- Properties need to be explicitly searched for using the search syntax `props.<property-name>:<property-value>`. This can be cumbersome if you want to quickly filter repositories by a property.
- Properties are only available for GitHub Enterprise Cloud and GitHub Enterprise Server. If you are using Free or Teams, you are out of luck.
- Properties are not clearly displayed on the repository page. You need to navigate to a special properties page to see them.
