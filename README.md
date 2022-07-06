# Personal

<html>
<head>
<style>
  body {
    font: 0.7rem sans-serif;
  }

  h1 {
    margin:  10px;
  }

  ul#episodes {
    float: left;
    margin:  0 10px;
    padding: 0;
    width: 35%;
  }

  ul#episodes > li {
    list-style-type: none;
  }

  button {
    border-radius:  7px;
    border: 0;
    background: #191414;
    color: #fff;
    padding:  10px;
    margin:  0 0 3px 0;
    width: 100%;
    cursor: pointer;
  }

  button:hover {
    background: #1Db954;
  }


</style>
  </head>
  <body>
    <h1>Pick an episode...</h1>
    <ul id="episodes">
      <li>
        <button data-spotify-id="spotify:episode:7makk4oTQel546B0PZlDM5">
          My Path to Spotify: Women in Engineering
        </button>
      </li>
      <li>
        <button data-spotify-id="spotify:episode:43cbJh4ccRD7lzM2730YK3">
          What is Backstage?
        </button>
      </li>
      <li>
        <button data-spotify-id="spotify:episode:6I3ZzCxRhRkNqnQNo8AZPV">
          Introducing Nerd Out@Spotify
        </button>
      </li>
    </ul>

    <div id="embed-iframe"></div>
    <script src="https://open.spotify.com/embed-podcast/iframe-api/v1" async>
    </script>
    <script type="text/javascript">
      window.onSpotifyIframeApiReady = (IFrameAPI) => {
        let element = document.getElementById('embed-iframe');
        let options = {
            width: '60%',
            height: '200',
            uri: 'spotify:episode:7makk4oTQel546B0PZlDM5'
          };
        let callback = (EmbedController) => {
          document.querySelectorAll('ul#episodes > li > button').forEach(
            episode => {
              episode.addEventListener('click', () => {
                EmbedController.loadUri(episode.dataset.spotifyId)
              });
            })
        };
        IFrameAPI.createController(element, options, callback);
      };
    </script>
  </body>
</html>

![github-contribution-grid-snake](https://user-images.githubusercontent.com/75934798/177515129-3f3ca972-c979-43bc-8538-718418aec817.gif)

