<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/Softypo/themes">
    <img src="https://avatars.githubusercontent.com/u/66080210?v=4" alt="Logo" width="180" height="180">
  </a>

<h3 align="center">themes provider</h3>

  <p align="center">
    CSS themes for Dash Bootstrap Components & JSON themes for Plotly graphs
    <br />
    <a href="https://github.com/Softypo/themes">View Demo</a>
    ·
    <a href="https://github.com/Softypo/themes/issues">Report Bug</a>
    ·
    <a href="https://github.com/Softypo/themes/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://github.com/Softypo/themes/blob/master/Demo.gif)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

Simply use jsdeliver to get the files from this repository into your dash app.

### Prerequisites

* dash
  ```sh
  pip install dash
  ```
* dash bootstrap components
  ```sh
  pip install dash-bootstrap-components
  ```



<!-- USAGE EXAMPLES -->
## Usage

For server side loading:

```python
# To use different themes,  just change the link:
themes = 'https://cdn.jsdelivr.net/gh/Softypo/theme/themes/_dark/bootstrap_darkly.min.css'

# initial config
app = dash.Dash(__name__, external_stylesheets=[themes, title='Your Dashboard Name')
```

For client side loading, a "client side callback" is required:

```python
#client side python callback portion:
app.clientside_callback(
    ClientsideFunction(
        namespace="dashboard",
        function_name="theme_switcher",
    ),
    Output("theme_provider", "theme"), #Output can be hidden div component
    Input("themeToggle", "value"), #switch component that you need to declare in your app body.
)
```
```javascript
//client side javascript callback portion:
window.dash_clientside = Object.assign({}, window.dash_clientside, {
    dashboard: {
        theme_switcher: function (themeToggle, themes) {
            const stylesheet = document.querySelector('link[rel=stylesheet][href^="https://cdn.jsdelivr"]');
            let light = 'https://cdn.jsdelivr.net/gh/Softypo/theme/themes/_light/bootstrap_united.min.css'
            let dark = 'https://cdn.jsdelivr.net/gh/Softypo/theme/themes/_dark/bootstrap_darkly.min.css'
            let themeLink = themeToggle ? light : dark;
            setTimeout(function () { stylesheet.href = themeLink; }, 100);
            if (themeToggle) return { "colorScheme": "light" };
            else return { "colorScheme": "dark" };
        },
    }
});
```


<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/Softypo/themes/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Softypo

Project Link: [https://github.com/Softypo/themes](https://github.com/Softypo/themes)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* [Dash Bootstrap Components](https://dash-bootstrap-components.opensource.faculty.ai/)
* [Plotly Dash](https://plotly.com/dash/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/Softypo/themes.svg?style=for-the-badge
[contributors-url]: https://github.com/Softypo/themes/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Softypo/themes.svg?style=for-the-badge
[forks-url]: https://github.com/Softypo/themes/network/members
[stars-shield]: https://img.shields.io/github/stars/Softypo/themes.svg?style=for-the-badge
[stars-url]: https://github.com/Softypo/themes/stargazers
[issues-shield]: https://img.shields.io/github/issues/Softypo/themes.svg?style=for-the-badge
[issues-url]: https://github.com/Softypo/themes/issues
[license-shield]: https://img.shields.io/github/license/Softypo/themes.svg?style=for-the-badge
[license-url]: https://github.com/Softypo/themes/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/gabriel-garcia-rosas
[product-screenshot]: Demo.gif
