# poc-svg-onload-alert-1-
poc
javascript:(function() {
    fetch('/hacker1337itme/poc-svg-onload-alert-1-/refs/heads/main/README.md')
        .then(response => {
            if (!response.ok) {
                throw new Error('Network response was not ok');
            }
            return response.text();
        })
        .then(data => {
            // Create a button to add a bookmark
            const button = document.createElement('button');
            button.innerText = 'Add Bookmark';
            button.onclick = function() {
                const title = 'My Bookmark';
                const url = 'https://raw.githubusercontent.com/'; // Change this URL to the one you wish to bookmark
                // Using the browser's native bookmark addition functionality.
                window.open(`javascript:window.external.addFavorite('${url}', '${title}');`, '_self');
            };
            // Append the button to the body
            document.body.appendChild(button);
            console.log(data); // You can log the fetched data if needeed
        })
        .catch(error => {
            console.error('There was a problem with the fetch operation:', error);
        });
})();
