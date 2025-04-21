# 🌐 Public CORS Proxies Guide

A curated list of public proxies to bypass Cross-Origin Resource Sharing (CORS) restrictions, useful for development, testing, or web scraping purposes.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0--1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

## 🚀 Quick Start

To quickly use a CORS proxy, prepend its URL to the target URL you want to access.  Make sure to encode the target URL using `encodeURIComponent`. See the examples below.

## ⚙️ Available Proxies

Here's a list of publicly available CORS proxies:

*   **AllOrigins**

    *   URL: `https://api.allorigins.win/raw?url=`
    *   Example:

        ```javascript
        fetch('https://api.allorigins.win/raw?url=' + encodeURIComponent('https://example.com/api'))
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(error => console.error('Error:', error));
        ```

*   **CorsProxy.io**

    *   URL: `https://corsproxy.io/?url=`
    *   Example:

        ```javascript
        fetch('https://corsproxy.io/?url=' + encodeURIComponent('https://api.example.com/data'))
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(error => console.error('Error:', error));
        ```

*   **Cors.lol**

    *   URL: `https://api.cors.lol/?url=`
    *   Limit: 1,000 requests/day
    *   Example:

        ```javascript
        fetch('https://api.cors.lol/?url=' + encodeURIComponent('https://data.example.com'))
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(error => console.error('Error:', error));
        ```

*   **ThingProxy**

    *   URL: `https://thingproxy.freeboard.io/fetch/`
    *   Example:

        ```javascript
        fetch('https://thingproxy.freeboard.io/fetch/https://example.net/resource')
        .then(response => response.text()) // or response.json() if the content is JSON
        .then(data => console.log(data))
        .catch(error => console.error('Error:', error));
        ```

*   **Universal CORS Proxy (Glitch)**

    *   URL: `https://universal-cors-proxy.glitch.me/fetch/`
    *   Example:

        ```javascript
        fetch('https://universal-cors-proxy.glitch.me/fetch/https://api.demo/items')
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(error => console.error('Error:', error));
        ```

## 🧑‍💻 Basic Usage

*   **Prepend the proxy URL:**

    ```javascript
    const url = 'https://corsproxy.io/?url=' + encodeURIComponent('https://your-api.com');
    ```

*   **Encode dynamic parameters:**

    ```javascript
    fetch('https://corsproxy.com/?url=' + encodeURIComponent('https://api.com/search?q=hello'))
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
    ```

*   **Handle errors:**

    ```javascript
    fetch('https://corsproxy.io/?url=' + encodeURIComponent('https://your-api.com'))
    .then(response => {
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error('Request failed:', error));
    ```

## ⚠️ Warnings

*   **Privacy:** Avoid sending sensitive data (e.g., passwords, API keys) through public proxies as you have no control over their security or logging practices.
*   **Limits:** Some services (e.g., Cloudflare) might block requests coming from public proxies.
*   **Reliability:** Public proxies may be slow, unreliable, or go offline unexpectedly.  Don't rely on them for production environments.
*   **Rate Limiting:** Be mindful of the proxy's rate limits to avoid being blocked.

## 🤔 Alternatives

*   **Host your own proxy:** Consider running your own proxy server (e.g., using [CORS Anywhere](https://github.com/Rob--W/cors-anywhere)) for more control and reliability.
*   **Backend Server:** Implement a server-side endpoint on your own domain that fetches the data and returns it to the client. This is the most secure and reliable solution.

## 🎯 Common Use Cases

*   Frontend development without backend access or while the backend is under development.
*   Accessing public APIs that do not include necessary CORS headers.
*   Quick prototyping or small, non-critical projects.
*   Web scraping for non-sensitive data.

## 📜 License

This guide is released under the [Public Domain (CC0)](http://creativecommons.org/publicdomain/zero/1.0/). Credits are appreciated but not required.

## 🤝 Contributing

To improve this guide, submit suggestions via issues or pull requests.  We welcome contributions!
