[https://apify.com/epctex/genius-scraper](https://apify.com/epctex/genius-scraper?fpr=yhdrb)

# Actor - Genius Scraper

## Genius scraper

The Genius.com scraper is a versatile tool designed to extract songs and lyrics from the popular music platform, Genius. With this powerful scraper, you can easily fetch songs and lyrics using various parameters such as song details, albums, artists, and tag detail pages. Whether you're looking for a specific song, exploring an artist's discography, or searching for songs based on specific tags, our scraper provides a seamless solution for accessing the desired music content from Genius.com. Unlock a wealth of musical knowledge and lyrics with our reliable and efficient Genius.com scraper.

The Genius.com data scraper offers a range of distinct features for versatile data retrieval:

-   Song detail - Extract songs and lyrics from individual song detail pages, providing comprehensive information about specific tracks.

-   Album detail: Gather songs and lyrics from album detail pages, allowing for a comprehensive view of a particular album's musical content.

-   Artist detail: Retrieve songs and lyrics from artist detail pages, providing access to a specific artist's discography and their corresponding lyrics.

-   Tags: Fetch song details and lyrics from tag pages, enabling exploration and extraction based on specific genres, themes, or labels.

-   Search: Utilize keyword and search mode parameters to conduct targeted searches, swiftly locating songs and lyrics that align with your specific criteria.

-   Comments: Customize your scraping preferences by specifying whether to include comments, tailoring the extracted data to focus solely on songs and lyrics, or incorporating user comments for a more comprehensive analysis.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/genius-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on Genius.com that should be visited. Required fields are:

- `search`: (Optional) (String) The keyword that you can search on Genius.

- `searchMode`: (Optional) (String) What type of search do you want to make at Genius.

- `startUrls`: (Optional) (Array) List of Genius.com URLs. You should only provide song, album, artist detail, and tag URLs.

- `includeComments`: (Optional) (Boolean) Should comments be included in songs. 

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to scrape over a specific list URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that is explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detailed requests. If the actor doesn't block very often it'll scrape 100 listings in 2 minutes with ~0.02-0.04 compute units.

### Genius.com Scraper Input example

```json
{
    "startUrls": [    
    "https://genius.com/Fifty-fifty-cupid-twin-version-lyrics",
    "https://genius.com/albums/Fifty-fifty/The-beginning-cupid",
    "https://genius.com/artists/Drake",
    "https://genius.com/tags/pop",
    "https://genius.com/search?q=tiktok"
  ],
  "search": "",
  "searchMode": "song",
  "includeComments": false,
    "proxy": {
        "useApifyProxy": true
    },
    "endPage": 5,
    "maxItems": 100
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## Genius.com Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Genius.com actor.

## Scraped Genius.com Properties

The structure of each item in Genius.com looks like this:

### Item Detail

```json
{
  "type": "song",
  "url": "https://genius.com/Post-malone-rockstar-lyrics",
  "id": 2942139,
  "lyrics": "<p>[Intro: Post Malone]<br>\n<a href=\"/12763178/Post-malone-rockstar/Hahahahaha\" data-id=\"12763178\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Hahahahaha</a><br>\n<a href=\"/17486928/Post-malone-rockstar/Tank-god\" data-id=\"17486928\" data-editorial-state=\"accepted\" data-classification=\"accepted\"><i>Tank God</i></a><br>\nAyy, ayy<br>\n<br>\n[Chorus: Post Malone]<br>\n<a href=\"/12694882/Post-malone-rockstar/Ive-been-fuckin-hoes-and-poppin-pillies-man-i-feel-just-like-a-rockstar-star-ayy-ayy\" data-id=\"12694882\" data-editorial-state=\"accepted\" data-classification=\"accepted\">I've been fuckin' hoes and poppin' pillies<br>\nMan, I feel just like a rockstar (Star, ayy, ayy)</a><br>\n<a href=\"/12696701/Post-malone-rockstar/All-my-brothers-got-that-gas-and-they-always-be-smokin-like-a-rasta-sta\" data-id=\"12696701\" data-editorial-state=\"accepted\" data-classification=\"accepted\">All my brothers got that gas<br>\nAnd they always be smokin' like a Rasta ('Sta)</a><br>\n<a href=\"/12704065/Post-malone-rockstar/Fuckin-with-me-call-up-on-a-uzi-and-show-up-man-them-the-shottas-tas-when-my-homies-pull-up-on-your-block-they-make-that-thing-go-grrra-ta-ta-ta-ta-pow-pow-pow-ayy-ayy\" data-id=\"12704065\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Fuckin' with me, call up on a Uzi<br>\nAnd show up, man, them the shottas ('Tas)<br>\nWhen my homies pull up on your block<br>\nThey make that thing go grrra-ta-ta-ta (Ta, pow, pow, pow, ayy, ayy)</a><br>\n<br>\n[Verse 1: Post Malone]<br>\n<a href=\"/12692495/Post-malone-rockstar/Switch-my-whip-came-back-in-black-im-startin-sayin-rest-in-peace-to-bon-scott-scott-ayy\" data-id=\"12692495\" class=\"has_comments\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Switch my whip, came back in black<br>\nI'm startin' sayin', \"Rest in peace to Bon Scott\" (Scott, ayy)</a><br>\n<a href=\"/12709785/Post-malone-rockstar/Close-that-door-we-blowin-smoke-she-ask-me-light-a-fire-like-im-morrison-son-ayy-act-a-fool-on-stage-prolly-leave-my-fuckin-show-in-a-cop-car-car-ayy\" data-id=\"12709785\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Close that door, we blowin' smoke<br>\nShe ask me light a fire like I'm Morrison ('Son, ayy)<br>\nAct a fool on stage<br>\nProlly leave my fuckin' show in a cop car (Car, ayy)</a><br>\n<a href=\"/12712321/Post-malone-rockstar/Shit-was-legendary-threw-a-tv-out-the-window-of-the-montage\" data-id=\"12712321\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Shit was legendary<br>\nThrew a TV out the window of the Montage</a><br>\n<a href=\"/12712779/Post-malone-rockstar/Cocaine-on-the-table-liquor-pourin-dont-give-a-damn\" data-id=\"12712779\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Cocaine on the table, liquor pourin', don't give a damn</a><br>\n<a href=\"/12692523/Post-malone-rockstar/Dude-your-girlfriend-is-a-groupie-she-just-tryna-get-in-sayin-im-with-the-band-ayy-ayy-now-she-actin-outta-pocket-tryna-grab-up-on-my-pants-hundred-bitches-in-my-trailer-say-they-aint-got-a-man-and-they-all-brought-a-friend-yeah-ayy-ayy-ayy\" data-id=\"12692523\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Dude, your girlfriend is a groupie, she just tryna get in<br>\nSayin', \"I'm with the band\" (Ayy, ayy)<br>\nNow she actin' outta pocket, tryna grab up on my pants<br>\nHundred bitches in my trailer say they ain't got a man<br>\nAnd they all brought a friend (Yeah, ayy, ayy, ayy)</a><br>\n<br>\n[Chorus: Post Malone]<br>\n<a href=\"/12694882/Post-malone-rockstar/Ive-been-fuckin-hoes-and-poppin-pillies-man-i-feel-just-like-a-rockstar-star-ayy-ayy\" data-id=\"12694882\" data-editorial-state=\"accepted\" data-classification=\"accepted\">I've been fuckin' hoes and poppin' pillies<br>\nMan, I feel just like a rockstar (Star, ayy, ayy)</a><br>\n<a href=\"/12696701/Post-malone-rockstar/All-my-brothers-got-that-gas-and-they-always-be-smokin-like-a-rasta-sta\" data-id=\"12696701\" data-editorial-state=\"accepted\" data-classification=\"accepted\">All my brothers got that gas<br>\nAnd they always be smokin' like a Rasta ('Sta)</a><br>\n<a href=\"/12704065/Post-malone-rockstar/Fuckin-with-me-call-up-on-a-uzi-and-show-up-man-them-the-shottas-tas-when-my-homies-pull-up-on-your-block-they-make-that-thing-go-grrra-ta-ta-ta-ta-pow-pow-pow-ayy-ayy\" data-id=\"12704065\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Fuckin' with me, call up on a Uzi<br>\nAnd show up, man, them the shottas ('Tas)<br>\nWhen my homies pull up on your block<br>\nThey make that thing go grrra-ta-ta-ta (Ta, pow, pow, pow)</a><br>\n<br>\n[Verse 2: 21 Savage]<br>\n<a href=\"/12699274/Post-malone-rockstar/Ive-been-in-the-hills-fuckin-superstars-feelin-like-a-popstar-21-21-21\" data-id=\"12699274\" class=\"has_comments\" data-editorial-state=\"accepted\" data-classification=\"accepted\">I've been in the Hills fuckin' superstars<br>\nFeelin' like a popstar (21, 21, 21)</a><br>\n<a href=\"/12823275/Post-malone-rockstar/Drankin-henny-bad-bitches-jumpin-in-the-pool\" data-id=\"12823275\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Drankin' Henny, bad bitches jumpin' in the pool</a><br>\nAnd they ain't got on no bra (Bra)<br>\n<a href=\"/12754722/Post-malone-rockstar/Hit-her-from-the-back-pullin-on-her-tracks-and-now-she-screamin-out-no-mas-yeah-yeah-yeah\" data-id=\"12754722\" class=\"has_comments\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Hit her from the back, pullin' on her tracks<br>\nAnd now she screamin' out, \"¡No más!\" (Yeah, yeah, yeah)</a><br>\n<a href=\"/12691290/Post-malone-rockstar/They-like-savage-why-you-got-a-12-car-garage-and-you-only-got-six-cars-21\" data-id=\"12691290\" class=\"has_comments\" data-editorial-state=\"accepted\" data-classification=\"accepted\">They like, \"Savage, why you got a 12 car garage<br>\nAnd you only got six cars?\" (21)</a><br>\n<a href=\"/12713628/Post-malone-rockstar/I-aint-with-the-cakin-how-you-kiss-that-kiss-that\" data-id=\"12713628\" class=\"has_comments\" data-editorial-state=\"accepted\" data-classification=\"accepted\">I ain't with the cakin', how you kiss that? (Kiss that?)</a><br>\nYour wifey say I'm lookin' like a whole snack (Big snack)<br>\n<a href=\"/12695873/Post-malone-rockstar/Green-hundreds-in-my-safe-i-got-old-racks-old-racks-la-bitches-always-askin-where-the-coke-at-21-21\" data-id=\"12695873\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Green hundreds in my safe, I got old racks (Old racks)<br>\nL.A. bitches always askin', \"Where the coke at?\" (21, 21)</a><br>\nLivin' like a rockstar, smash out on a cop car<br>\n<a href=\"/12710153/Post-malone-rockstar/Sweeter-than-a-pop-tart-you-know-you-are-not-hard\" data-id=\"12710153\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Sweeter than a Pop-Tart, you know you are not hard</a><br>\n<a href=\"/12696231/Post-malone-rockstar/I-done-made-the-hot-chart-member-i-used-to-trap-hard\" data-id=\"12696231\" class=\"has_pending_edits\" data-editorial-state=\"accepted\" data-classification=\"accepted\">I done made the hot chart, 'member I used to trap hard</a><br>\n<a href=\"/12694882/Post-malone-rockstar/Ive-been-fuckin-hoes-and-poppin-pillies-man-i-feel-just-like-a-rockstar-star-ayy-ayy\" data-id=\"12694882\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Livin' like a rockstar, I'm livin' like a rockstar (<i>Ayy</i>)</a><br>\n<br>\n[Chorus: Post Malone &amp; <i>21</i><i> Savage</i>]<br>\n<a href=\"/12694882/Post-malone-rockstar/Ive-been-fuckin-hoes-and-poppin-pillies-man-i-feel-just-like-a-rockstar-star-ayy-ayy\" data-id=\"12694882\" data-editorial-state=\"accepted\" data-classification=\"accepted\">I've been fuckin' hoes and poppin' pillies<br>\nMan, I feel just like a rockstar (Star, ayy, ayy)</a><br>\n<a href=\"/12696701/Post-malone-rockstar/All-my-brothers-got-that-gas-and-they-always-be-smokin-like-a-rasta-sta\" data-id=\"12696701\" data-editorial-state=\"accepted\" data-classification=\"accepted\">All my brothers got that gas<br>\nAnd they always be smokin' like a Rasta ('Sta, <i>yeah, yeah, yeah, yeah</i>)</a><br>\n<a href=\"/12704065/Post-malone-rockstar/Fuckin-with-me-call-up-on-a-uzi-and-show-up-man-them-the-shottas-tas-when-my-homies-pull-up-on-your-block-they-make-that-thing-go-grrra-ta-ta-ta-ta-pow-pow-pow-ayy-ayy\" data-id=\"12704065\" data-editorial-state=\"accepted\" data-classification=\"accepted\">Fuckin' with me, call up on a Uzi<br>\nAnd show up, man, them the shottas ('Tas)<br>\nWhen my homies pull up on your block<br>\nThey make that thing go grrra-ta-ta-ta (Ta, grrra-ta-ta-ta-ta)</a><br>\n<br>\n[Outro: Post Malone]<br>\n<a href=\"/12694882/Post-malone-rockstar/Ive-been-fuckin-hoes-and-poppin-pillies-man-i-feel-just-like-a-rockstar-star-ayy-ayy\" data-id=\"12694882\" data-editorial-state=\"accepted\" data-classification=\"accepted\"><i>Star, star, rockstar, rockstar, star</i><br>\nRockstar<br>\n<i>Rockstar, feel just like a–</i><br>\nRockstar<br>\n<i>Rockstar</i><br>\nRockstar<br>\n<i>Feel just like a...</i></a></p>\n\n",
  "artists": [
    {
      "url": "https://genius.com/artists/Post-malone",
      "id": 326362,
      "name": "Post Malone",
      "imageUrl": "https://images.genius.com/6771553aba28386ce3b7ee55724d43c2.1000x1000x1.jpg",
      "isVerified": true
    }
  ],
  "albums": [
    {
      "albumId": 326339,
      "albumName": "beerbongs & bentleys",
      "coverArtThumbnailUrl": "https://images.genius.com/ef176757a5735c7a104dd735543c1d20.300x300x1.png",
      "coverArt": "https://images.genius.com/ef176757a5735c7a104dd735543c1d20.1000x1000x1.png",
      "title": "beerbongs & bentleys by Post Malone",
      "url": "https://genius.com/albums/Post-malone/Beerbongs-bentleys"
    }
  ],
  "relatedSongs": [
    {
      "id": 2942139,
      "url": "https://genius.com/Post-malone-rockstar-lyrics",
      "title": "​​rockstar"
    },
    {
      "id": 2961138,
      "url": "https://genius.com/Post-malone-psycho-lyrics",
      "title": "Psycho"
    },
    {
      "id": 3007474,
      "url": "https://genius.com/Post-malone-candy-paint-lyrics",
      "title": "Candy Paint"
    },
    {
      "id": 3627785,
      "url": "https://genius.com/Post-malone-stay-lyrics",
      "title": "Stay"
    },
    {
      "id": 3646558,
      "url": "https://genius.com/Post-malone-paranoid-lyrics",
      "title": "Paranoid"
    },
    {
      "id": 3646559,
      "url": "https://genius.com/Post-malone-same-bitches-lyrics",
      "title": "Same Bitches"
    },
    {
      "id": 3646560,
      "url": "https://genius.com/Post-malone-blame-it-on-me-lyrics",
      "title": "Blame It On Me"
    },
    {
      "id": 3646561,
      "url": "https://genius.com/Post-malone-92-explorer-lyrics",
      "title": "92 Explorer"
    },
    {
      "id": 3646562,
      "url": "https://genius.com/Post-malone-otherside-lyrics",
      "title": "Otherside"
    },
    {
      "id": 3646563,
      "url": "https://genius.com/Post-malone-takin-shots-lyrics",
      "title": "Takin’ Shots"
    },
    {
      "id": 3646564,
      "url": "https://genius.com/Post-malone-over-now-lyrics",
      "title": "Over Now"
    },
    {
      "id": 3646565,
      "url": "https://genius.com/Post-malone-sugar-wraith-lyrics",
      "title": "Sugar Wraith"
    },
    {
      "id": 3646566,
      "url": "https://genius.com/Post-malone-zack-and-codeine-lyrics",
      "title": "Zack and Codeine"
    },
    {
      "id": 3646567,
      "url": "https://genius.com/Post-malone-jonestown-interlude-lyrics",
      "title": "Jonestown (Interlude)"
    },
    {
      "id": 3646568,
      "url": "https://genius.com/Post-malone-better-now-lyrics",
      "title": "Better Now"
    },
    {
      "id": 3646569,
      "url": "https://genius.com/Post-malone-spoil-my-night-lyrics",
      "title": "Spoil My Night"
    },
    {
      "id": 3646570,
      "url": "https://genius.com/Post-malone-rich-and-sad-lyrics",
      "title": "Rich & Sad"
    },
    {
      "id": 3646571,
      "url": "https://genius.com/Post-malone-ball-for-me-lyrics",
      "title": "Ball For Me"
    }
  ],
  "producedBy": [
    {
      "id": 1112844,
      "title": "Tank God",
      "url": "https://genius.com/artists/Tank-god"
    },
    {
      "id": 143754,
      "title": "Louis Bell",
      "url": "https://genius.com/artists/Louis-bell"
    }
  ],
  "writtenBy": [
    {
      "id": 1112844,
      "title": "Tank God",
      "url": "https://genius.com/artists/Tank-god"
    },
    {
      "id": 1668463,
      "title": "Carl Rosen",
      "url": "https://genius.com/artists/Carl-rosen"
    },
    {
      "id": 18047,
      "title": "Joey Bada$$",
      "url": "https://genius.com/artists/Joey-bada"
    },
    {
      "id": 143754,
      "title": "Louis Bell",
      "url": "https://genius.com/artists/Louis-bell"
    },
    {
      "id": 430404,
      "title": "21 Savage",
      "url": "https://genius.com/artists/21-savage"
    },
    {
      "id": 326362,
      "title": "Post Malone",
      "url": "https://genius.com/artists/Post-malone"
    }
  ],
  "tags": [
    {
      "url": "https://genius.com/tags/atlanta-rap",
      "isPrimary": false,
      "name": "Atlanta Rap",
      "id": 3636
    },
    {
      "url": "https://genius.com/tags/cloud-rap",
      "isPrimary": false,
      "name": "Cloud Rap",
      "id": 2916
    },
    {
      "url": "https://genius.com/tags/pop-rap",
      "isPrimary": false,
      "name": "Pop Rap",
      "id": 3970
    },
    {
      "url": "https://genius.com/tags/pop",
      "isPrimary": true,
      "name": "Pop",
      "id": 16
    },
    {
      "url": "https://genius.com/tags/dark-pop",
      "isPrimary": false,
      "name": "Dark Pop",
      "id": 2788
    },
    {
      "url": "https://genius.com/tags/rap",
      "isPrimary": true,
      "name": "Rap",
      "id": 1434
    }
  ],
  "media": [
    {
      "url": "https://open.spotify.com/track/1OmcAT5Y8eg5bUPv9qJT4R",
      "type": "audio",
      "provider": "spotify",
      "nativeUri": "spotify:track:1OmcAT5Y8eg5bUPv9qJT4R"
    },
    {
      "url": "https://soundcloud.com/postmalone/rockstar-feat-21-savage",
      "type": "audio",
      "provider": "soundcloud",
      "attribution": "postmalone"
    },
    {
      "url": "http://www.youtube.com/watch?v=UceaB4D0jpo",
      "type": "video",
      "start": 12,
      "provider": "youtube"
    }
  ],
  "customPerformances": [
    {
      "label": "Performance Rights",
      "artists": [
        {
          "id": 551598,
          "url": "https://genius.com/artists/Ascap",
          "name": "ASCAP",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/cd12f3f393d30794d4d085567fa6693e.900x900x1.jpg"
        },
        {
          "id": 1138091,
          "url": "https://genius.com/artists/Bmi",
          "name": "BMI",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/051b0a6beabf8a9eb8768e9f874a542f.1000x1000x1.jpg"
        },
        {
          "id": 3203462,
          "url": "https://genius.com/artists/Songview",
          "name": "SongView",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/046e3c633307e5fcd9ca85274270c867.600x600x1.jpg"
        }
      ]
    },
    {
      "label": "Publisher",
      "artists": [
        {
          "id": 1710098,
          "url": "https://genius.com/artists/Roba-music-publishing",
          "name": "ROBA Music Publishing",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/c3dad93b4d939b50666ecfb4d2740936.1000x1000x1.png"
        },
        {
          "id": 1011919,
          "url": "https://genius.com/artists/Bmg",
          "name": "BMG",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/d7674e632d4ffeb66c78b9a2ec56f32e.400x400x1.jpg"
        },
        {
          "id": 2263295,
          "url": "https://genius.com/artists/Felicimi",
          "name": "Felicimi",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 2153218,
          "url": "https://genius.com/artists/Sony-atv-allegro",
          "name": "Sony/ATV Allegro",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 1615581,
          "url": "https://genius.com/artists/Slaughter-gang",
          "name": "Slaughter Gang",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/49cc005d21e544b8337c2c6de25d41b2.670x670x1.png"
        },
        {
          "id": 2234993,
          "url": "https://genius.com/artists/Posty-publishing",
          "name": "Posty Publishing",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 2248863,
          "url": "https://genius.com/artists/Joeybad-publishing",
          "name": "JoeyBad Publishing",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 1525200,
          "url": "https://genius.com/artists/Electric-feel",
          "name": "Electric Feel",
          "isVerified": true,
          "imageUrl": "https://images.genius.com/a34cb17853582bae96f6c3a6ed60abb2.200x200x1.png"
        },
        {
          "id": 1544670,
          "url": "https://genius.com/artists/Reservoir-media",
          "name": "Reservoir Media",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/63ea161392ca63c9f79015c93ad5d2f5.200x200x1.png"
        },
        {
          "id": 1104563,
          "url": "https://genius.com/artists/Universal-music-group",
          "name": "Universal Music Group",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/7b3fb2c00317cb2eb2453f9f4e7473d1.600x600x1.png"
        },
        {
          "id": 647230,
          "url": "https://genius.com/artists/Emi-april-music",
          "name": "EMI April Music",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 992360,
          "url": "https://genius.com/artists/Bmg-gold-songs",
          "name": "BMG Gold Songs",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 88331,
          "url": "https://genius.com/artists/Sony-music-entertainment",
          "name": "Sony Music Entertainment",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/2a8cce70d4827d126ecbbc648a8ad62f.1000x1000x1.png"
        }
      ]
    },
    {
      "label": "Recording Engineer",
      "artists": [
        {
          "id": 1690048,
          "url": "https://genius.com/artists/Lorenzo-cardona",
          "name": "Lorenzo Cardona",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 1179666,
          "url": "https://genius.com/artists/Ethan-stevens",
          "name": "Ethan Stevens",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/6a3a29d89cf2de59b5bb92ddba7fd78d.813x813x1.jpg"
        },
        {
          "id": 143754,
          "url": "https://genius.com/artists/Louis-bell",
          "name": "Louis Bell",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/e5e5ab07410bcde1d4bc916ee86f6ec1.727x727x1.jpg"
        }
      ]
    },
    {
      "label": "Studio Personnel",
      "artists": [
        {
          "id": 1690048,
          "url": "https://genius.com/artists/Lorenzo-cardona",
          "name": "Lorenzo Cardona",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 143754,
          "url": "https://genius.com/artists/Louis-bell",
          "name": "Louis Bell",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/e5e5ab07410bcde1d4bc916ee86f6ec1.727x727x1.jpg"
        },
        {
          "id": 1179666,
          "url": "https://genius.com/artists/Ethan-stevens",
          "name": "Ethan Stevens",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/6a3a29d89cf2de59b5bb92ddba7fd78d.813x813x1.jpg"
        },
        {
          "id": 635518,
          "url": "https://genius.com/artists/Manny-marroquin",
          "name": "Manny Marroquin",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/312dc5aab4cf9f3040fc0e2fd05a9034.661x539x1.jpg"
        }
      ]
    },
    {
      "label": "Phonographic Copyright ℗",
      "artists": [
        {
          "id": 1104563,
          "url": "https://genius.com/artists/Universal-music-group",
          "name": "Universal Music Group",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/7b3fb2c00317cb2eb2453f9f4e7473d1.600x600x1.png"
        },
        {
          "id": 1011844,
          "url": "https://genius.com/artists/Republic-records",
          "name": "Republic Records",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/d8ea37a285aa8bdcb0eaebb31f116529.1000x1000x1.jpg"
        }
      ]
    },
    {
      "label": "Copyright ©",
      "artists": [
        {
          "id": 1104563,
          "url": "https://genius.com/artists/Universal-music-group",
          "name": "Universal Music Group",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/7b3fb2c00317cb2eb2453f9f4e7473d1.600x600x1.png"
        },
        {
          "id": 1011844,
          "url": "https://genius.com/artists/Republic-records",
          "name": "Republic Records",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/d8ea37a285aa8bdcb0eaebb31f116529.1000x1000x1.jpg"
        }
      ]
    },
    {
      "label": "Instrumentation",
      "artists": [
        {
          "id": 1112844,
          "url": "https://genius.com/artists/Tank-god",
          "name": "Tank God",
          "isVerified": true,
          "imageUrl": "https://images.genius.com/cfd791d27335fe4442ba1aaee85cac99.1000x1000x1.jpg"
        },
        {
          "id": 143754,
          "url": "https://genius.com/artists/Louis-bell",
          "name": "Louis Bell",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/e5e5ab07410bcde1d4bc916ee86f6ec1.727x727x1.jpg"
        }
      ]
    },
    {
      "label": "Programmer",
      "artists": [
        {
          "id": 1112844,
          "url": "https://genius.com/artists/Tank-god",
          "name": "Tank God",
          "isVerified": true,
          "imageUrl": "https://images.genius.com/cfd791d27335fe4442ba1aaee85cac99.1000x1000x1.jpg"
        },
        {
          "id": 143754,
          "url": "https://genius.com/artists/Louis-bell",
          "name": "Louis Bell",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/e5e5ab07410bcde1d4bc916ee86f6ec1.727x727x1.jpg"
        }
      ]
    },
    {
      "label": "Mixing Engineer",
      "artists": [
        {
          "id": 635518,
          "url": "https://genius.com/artists/Manny-marroquin",
          "name": "Manny Marroquin",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/312dc5aab4cf9f3040fc0e2fd05a9034.661x539x1.jpg"
        }
      ]
    },
    {
      "label": "Label",
      "artists": [
        {
          "id": 1011844,
          "url": "https://genius.com/artists/Republic-records",
          "name": "Republic Records",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/d8ea37a285aa8bdcb0eaebb31f116529.1000x1000x1.jpg"
        }
      ]
    },
    {
      "label": "Mastering Engineer",
      "artists": [
        {
          "id": 647414,
          "url": "https://genius.com/artists/Mike-bozzi",
          "name": "Mike Bozzi",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/0ec0a44b755cb745add8e3b72754a630.400x400x1.jpg"
        }
      ]
    },
    {
      "label": "Artwork",
      "artists": [
        {
          "id": 1221286,
          "url": "https://genius.com/artists/Dario-alva",
          "name": "Darío Alva",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 223628,
          "url": "https://genius.com/artists/Bryan-rivera",
          "name": "Bryan Rivera",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        },
        {
          "id": 1025904,
          "url": "https://genius.com/artists/Travis-brothers",
          "name": "Travis Brothers",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        }
      ]
    },
    {
      "label": "Video Director",
      "artists": [
        {
          "id": 665888,
          "url": "https://genius.com/artists/Emil-nava",
          "name": "Emil Nava",
          "isVerified": false,
          "imageUrl": "https://images.genius.com/2bcafa68624001dbcd4ee853afdbe4e0.469x469x1.jpg"
        }
      ]
    },
    {
      "label": "Video Director Of Photography",
      "artists": [
        {
          "id": 1265422,
          "url": "https://genius.com/artists/Kramer-morgenthau",
          "name": "Kramer Morgenthau",
          "isVerified": false,
          "imageUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
        }
      ]
    }
  ],
  "contributors": [
    {
      "id": 30939,
      "iq": 28111,
      "url": "https://genius.com/TheDon",
      "role": "editor",
      "name": "TheDon",
      "avatarUrl": "https://images.genius.com/avatars/medium/fb2e0b677bf61fcc2e8b8a9fb49f0b53",
      "summary": "Fan of UK and US rap. Appreciate great bars and lyricism, but also enjoy the occasional Future and Gucci Mane. You’ll see me annotating mainly on UK artists because those are the bars I find easiest to decipher, or transcribing new songs, along with the occasional American annotations.\n\nFavourite rappers: Nas, Kendrick Lamar, The Notorious B.I.G., Lil Wayne,Wiley, Skepta, Kano, Dave, Lowkey\n\nFavourite artists: Kid Cudi, Kanye West, Travis Scott, Future, Young Thug\n\n(Yes, there is a difference between hip hop rappers and hip hop artists!)"
    },
    {
      "id": 78276,
      "iq": 87695,
      "url": "https://genius.com/infiniteintellect",
      "role": "contributor",
      "name": "infiniteintellect",
      "avatarUrl": "https://images.genius.com/avatars/medium/51ef21d60d5d0356fa62085e670f422c",
      "summary": ""
    },
    {
      "id": 271096,
      "iq": 482485,
      "url": "https://genius.com/Empath",
      "role": "staff",
      "name": "Colby Handy",
      "avatarUrl": "https://images.genius.com/87b485555d6ecb9d5a6c2af59ac97dde.560x603x28.gif",
      "summary": "Product @ Genius\n\nIf you need timely site support from staff, please reach out to @streetlights, @WriteNProppa, @killersnowtiger, @Gary, @louiedro, or @worstofalltime instead of me.\n\nOtherwise, feel free to shoot me a message and say hi!\n\n❄️🐝\n\n\n\n\nLearn how to annotate, transcribe, add song facts, and earn roles by reading our guides.\nTag @transcribers for help with lyrics and @genius-editorial-board and @mentors for help with annotations.\nStay in touch with new site features and fun projects by following the Genius Updates forum.\nGet involved with other contributors by creating or joining discussions in the Music, Genius Ideas, and Genius Help forums, or joining the Genius community Discord. \nReport problems with the website in the Bugs forum."
    },
    {
      "id": 1176499,
      "iq": 22853,
      "url": "https://genius.com/Ali_EmJay",
      "role": "editor",
      "name": "Ali_EmJay",
      "avatarUrl": "https://images.genius.com/avatars/medium/fc9448911728ba0e110ffde7a37f769e",
      "summary": "journalist / writer / translator\n\n\nEmail: Juwedy@Gmail.com   \n\nIf I have rejected your tate/suggestion and wanna know why, feel free to send a message (or for anything else, I guess)\n\n\n\nMy Telegram Channel  \n\nArtists I’ve helped get verified:\n- Suki Waterhouse\n- Sister\n- Ghostly Kisses\n- Coals\n- Havana"
    },
    {
      "id": 1710294,
      "iq": 201130,
      "url": "https://genius.com/SpeckHelper",
      "role": "moderator",
      "name": "Austin Rotter",
      "avatarUrl": "https://images.genius.com/avatars/medium/34770935d89496157e42990ae26e5acc",
      "summary": "DM me if you need help!\n\n\n\n\nThe info below is primarily for me to track my contributions\n\n\n\n\nMilestones\n\nJoined Genius/First Tate: May 3, 2015  \nMade Editor: January 27, 2017  \n20,000 IQ: August 7, 2017  \n30,000 IQ: November 16, 2017  \n40,000 IQ: December 15, 2017  \n50,000 IQ: January 1, 2018  \nMade Moderator: February 15, 2018  \n75,000 IQ: March 6, 2018  \n100,000 IQ: September 13, 2018  \n150,000 IQ: September 6, 2019  \n175,000 IQ: August 6, 2020  \n200,000 IQ: December 4, 2022\n\n\n\n\n\n\nMost Popular Transcriptions (>250k)\n\nPost Malone ft. Ty Dolla $ign -- \"Psycho\" (3,070,000)  \nPost Malone & Swae Lee -- \"Sunflower\" (2,450,000)  \nEminem -- \"Kamikaze\" (2,150,000)  \nPost Malone -- \"Circles\" (1,860,000)  \nThe Weeknd & Kendrick Lamar -- \"Pray For Me\" (1,120,000)  \nPost Malone ft. Young Thug -- \"Goodbyes\" (1,080,000)  \nMarshmello & Lil Peep -- \"Spotlight\" (830,000)  \nPost Malone ft. Ozzy Osbourne & Travis Scott -- \"Take What You Want\" (755,000)  \nPost Malone -- \"Over Now\" (735,000)  \nNF -- \"Lie\" (635,000)  \nBig Sean & Metro Boomin -- \"So Good\" (610,000)  \nJ. Cole -- \"BRACKETS\" (550,000)  \nMigos ft. Post Malone -- \"Notice Me\" (520,000)  \nLogic -- \"Confessions of a Dangerous Mind\" (495,000)  \nPost Malone -- \"92 Explorer\" (485,000)  \nDrake -- \"Peak\" (440,000)  \nPost Malone ft. Swae Lee -- \"Spoil My Night\" (425,000)  \nDrake ft. Ty Dolla $ign -- \"After Dark\" (405,000)  \nEminem -- \"Remind Me\" (355,000)  \nMigos & Marshmello -- \"Danger\" (320,000)  \n21 Savage ft. Post Malone -- \"all my friends\" (317,000)  \nPost Malone -- \"Blame It On Me\" (315,000)  \nPost Malone & The Weeknd -- \"One Right Now\" (300,000)  \nTravis Scott & Quavo -- \"Motorcycle Patches\" (280,000)\n\n\n\n\n\n\nMiscellaneous\n\n  \nMonthly Awards  \nGenius of the Month (February 2018)  \nBest Annotation of June 2019  \nBest Annotation of July 2019  \n13th Best Annotation of 2019  \nArticles  \nRATL beerbongs & bentleys  \nPost Malone's Stoney sets new record  \nMarshmello x Fortnite Concert  \nNF Reflects On Fame With \"The Search\"  \nRATL Hollywood's Bleeding\n\n\n\n\n\n\nCommunity List Blurbs\n\n  \nYear-End Best of 2017  \nStoney by Post Malone | \"rockstar\" by Post Malone  \nMost Anticipated Albums of 2018  \nbeerbongs & bentleys by Post Malone  \nMid-Year Best of 2018  \nbeerbongs & bentleys by Post Malone | \"Psycho\" by Post Malone | \"FRIENDS\" by Marshmello & Anne-Marie  \nYear-End Best of 2018  \nbeerbongs & bentleys by Post Malone | \"Psycho\" by Post Malone | \"Nice For What\" by Drake  \n100 Best Albums of the 2010s  \nStoney by Post Malone  \nYear-End Best of 2019  \nHollywood's Bleeding by Post Malone"
    },
    {
      "id": 1743222,
      "iq": 54596,
      "url": "https://genius.com/gone_11d2u_aa7b",
      "role": "contributor",
      "name": "gone_11d2u_aa7b",
      "avatarUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564",
      "summary": ""
    },
    {
      "id": 1827058,
      "iq": 79613,
      "url": "https://genius.com/NSRE",
      "role": "editor",
      "name": "NSRE",
      "avatarUrl": "https://images.genius.com/avatars/medium/7efded331d43d35f109d196bb9db7291",
      "summary": "A few achievements on Genius that I’m proud of:\n\n#1 Annotation June 2018\n#2 Annotation September 2018\n\nGetting my tates featured in these articles:\n\n\nWhat Does Frank Ocean’s “I Got Two Versions” Line Mean?\nNicki Minaj Has More To Say About Remy Ma & Papoose On DJ Khaled’s “I Can’t Even Lie”. Pretty sure Complex also lifted the tate\nThe Weeknd Appears To Sing About His Ex-Girlfriend Bella Hadid On “Wasted Times”.\nNAV Escalates His Beef With ‘XXL’ Following His “Freshman List” Song.\nMigos Reunite With Drake On Their New ‘Culture II’ Song “Walk It Talk It”.\nLil Wayne Showcases His Influence With Barack Obama & 2 Chainz Samples On “Dedicate”\n\n\n\nTates I heavily contributed to featured in:\n\n\nChris Brown & Joyner Lucas’ “Stranger Things” Samples The Hit Netflix Show’s Theme Song\nHow ‘Black Panther: The Album’ Connects With The Plot Of The Film\nDrake and Lil Wayne Both Reference The Cash Money Lawsuit On Their New “Family Feud” Remix\n\n\n\nHighest contributor score on My Dear, Melancholy, ye and Kids See Ghosts.\n\nShoulder-tapped by @ewokABdevito"
    },
    {
      "id": 1837201,
      "iq": 1802454,
      "url": "https://genius.com/Qatarsi",
      "role": "moderator",
      "name": "Qatarsi",
      "avatarUrl": "https://images.genius.com/avatars/medium/5aaca3dada7deba08627e6f87d6c683c",
      "summary": "In claris non fit interpretatio.\n\nGenius Italia\n\n\n\n\n NB: Se elimino una tua annotazione e ti domandi il motivo, controlla meglio nelle notifiche: la risposta è già lì. Se continua a non tornarti qualcosa, dai un'occhiata alle regole di Genius relative alle annotazioni.\n\n\n\n\nOFF LYRICS IG\n\nOFF LYRICS YT"
    },
    {
      "id": 2032874,
      "iq": 26670,
      "url": "https://genius.com/Hedi98",
      "role": "contributor",
      "name": "Hedi98",
      "avatarUrl": "https://s3.amazonaws.com/filepicker-images-rapgenius/posgijpegt",
      "summary": "#4 Chris Brown\n20K IQ Hit -15/07/18"
    },
    {
      "id": 2793634,
      "iq": 348673,
      "url": "https://genius.com/WiktorFraniak",
      "role": "editor",
      "name": "WiktorFraniak",
      "avatarUrl": "https://s3.amazonaws.com/filepicker-images-rapgenius/1nh2k3e2wxf",
      "summary": "Siema! ;D Jestem Wiktor i od września 2016 działam tutaj jako editor i członek ekipy RGPL. Jeśli masz jakieś pytania, problemy – napisz do mnie, a chętnie ci pomogę.\n\n  \n\n\n\nInstagram\nlast.fm\n\nWhosampled"
    },
    {
      "id": 2962216,
      "iq": 67217,
      "url": "https://genius.com/lxns",
      "role": "editor",
      "name": "lxns",
      "avatarUrl": "https://images.genius.com/avatars/medium/7dc1da168560a92ebaa8f0adb58b4be2",
      "summary": "Mostly inactive, but I’ll clean up inaccurate info if I come across it."
    },
    {
      "id": 3025667,
      "iq": 2791,
      "url": "https://genius.com/Yeezari",
      "role": "verified_artist",
      "name": "Yeezari",
      "avatarUrl": "https://images.genius.com/avatars/medium/10d4ee01a7f1d2ecfba3aa826ce9fa41",
      "summary": "Once a young and upcoming rapper from Sydney, Yeezari was an Australian-Iranian rapper with dynamic flows and rhyme schemes.\n\nThis versatility was evident, from tracks like “Big"
    },
    {
      "id": 3409147,
      "iq": 65772,
      "url": "https://genius.com/AndyBelt",
      "role": "editor",
      "name": "AndyBelt",
      "avatarUrl": "https://images.genius.com/avatars/medium/93d8bb7265364dffedebfbd22c0f8e96",
      "summary": "Music Fanatic (occasional Zealot)"
    },
    {
      "id": 4478046,
      "iq": 38180,
      "url": "https://genius.com/DennisTheTennis",
      "role": "editor",
      "name": "DennisTheTennis",
      "avatarUrl": "https://s3.amazonaws.com/filepicker-images-rapgenius/jEWnphclRxy6e0Etciin_jay-z-nas-2013-04-10-300x300.jpg",
      "summary": "If you have any questions, feel free to shoot me a message!"
    },
    {
      "id": 4670710,
      "iq": 239794,
      "url": "https://genius.com/MrBroezzz",
      "role": "editor",
      "name": "MrBroezzz",
      "avatarUrl": "https://images.genius.com/avatars/medium/78ee8a5cd03cc4e7c7d96532cb70a413",
      "summary": "Dutch-English-French-German | 24 |\n\nIf you have a question, DM me!"
    },
    {
      "id": 4796740,
      "iq": 997,
      "url": "https://genius.com/SCARXX",
      "role": "contributor",
      "name": "SCARXX",
      "avatarUrl": "https://images.genius.com/avatars/medium/5f8387df5a63c8fee55bf229e7df8b69",
      "summary": "I listen to Hip-Hop (Scarlxrd, Comethazine, Members Only, D Savage and more)"
    },
    {
      "id": 5243064,
      "iq": 38451,
      "url": "https://genius.com/Lockshores",
      "role": "moderator",
      "name": "Victor R.",
      "avatarUrl": "https://images.genius.com/avatars/medium/57e8bbe32504d40059d5110502a5696b",
      "summary": "Genius France"
    },
    {
      "id": 5310932,
      "iq": 59625,
      "url": "https://genius.com/RobMilli",
      "role": "editor",
      "name": "RobMilli",
      "avatarUrl": "https://s3.amazonaws.com/filepicker-images-rapgenius/n0b09h91i9s",
      "summary": "Milestones\n\nJoined Genius – 10/12/17\n1,000 IQ – 6/28/18\n5,000 IQ – 8/5/18\nTate Featured In Article – 8/20/18\n10,000 IQ – 8/22/18\nBest Annotations of August 2018 – 9/3/18\n15,000 IQ – 9/13/18\n20,000 IQ – 10/4/18\nTate Linked In Article – 10/13/18\n25,000 IQ – 10/27/18\nTate Written Out In Article – 11/2/18\nTate Featured In Article – 11/21/18\n30,000 IQ – 11/22/18\nTate Mentioned In Article – 11/22/18\nEditor and Rookie of the Year – 12/12/18\n40,000 IQ – 1/3/19\n50,000 IQ – 3/1/20\nGot a Real Life – 3/2/20\n\n  \n\n\nFavorite Albums of All Time\n\n-The Marshall Mathers LP\n-My Dear Melancholy,\n-Illmatic\n-CARE FOR ME\n-Victory Lap\n-B4.DA.$$\n-The Eminem Show\n-Views\n-The Infamous\n-Feed tha Streets II\n-1999\n-KOD\n-Lifestylez ov da Poor & Dangerous\n-Savage Mode\n-The Slim Shady LP\n-Signed To The Streets 3\n-2014 Forest Hills Drive\n-Slauson Boy 2\n-Artist\n\n  \n\n\nEditor\n\nBecame an Editor on 7/23/18 (Special thanks to @EwokABdevito, @IoShady, and @VinylZombie_MCR)"
    },
    {
      "id": 5754203,
      "iq": 30341,
      "url": "https://genius.com/jochnrochn",
      "role": "editor",
      "name": "jochnrochn",
      "avatarUrl": "https://s3.amazonaws.com/filepicker-images-rapgenius/oswtdtcz7y",
      "summary": ""
    },
    {
      "id": 6393487,
      "iq": 166,
      "url": "https://genius.com/BigDashie",
      "role": null,
      "name": "BigDashie",
      "avatarUrl": "https://s3.amazonaws.com/filepicker-images-rapgenius/tm9ztkjudg",
      "summary": "I listen to hella hip hop music."
    },
    {
      "id": 6790749,
      "iq": 71849,
      "url": "https://genius.com/FinoyElegante",
      "role": "editor",
      "name": "FinoyElegante",
      "avatarUrl": "https://images.genius.com/avatars/medium/44a890c24797c98e18ea5f7cdd69d3f6",
      "summary": ""
    },
    {
      "id": 9710542,
      "iq": 22802,
      "url": "https://genius.com/xsoul",
      "role": "transcriber",
      "name": "​​x$oul",
      "avatarUrl": "https://images.genius.com/84350513d7dde46bbf842bca644d910d.320x320x1.jpg",
      "summary": "pt & eng\n\n\n\n\n916\n\n\n\n\n\n\nAll my Transcriptions\n What I Listen to\n\nSocials\n\n\n\nImportant Dates:\n\n\n\n\n  \nAccount Created – November 7, 2019  \n1,000 IQ – May 1, 2021  \n5,000 IQ – November 17, 2021  \n\nTranscriber – February 14, 2022  \n10,000 IQ – March 4, 2022  \n15,000 IQ – April 13, 2022  \n20,000 IQ – December 17, 2022  \n\n\n\n\n\nSome of my favorite artists:\n\n\n\n➭ 916frosty\n➭ Yeat\n➭ 1nonly\n➭ $UICIDEBOY$\n➭ Shady Moon\n➭ lilbubblegum\n\n\n\n✧ Special thanks to Coolrrrray for the mentoring & CG7777 + Ferb for granting me the Transcriber role!"
    },
    {
      "name": "Aaditya",
      "avatarUrl": "https://assets.genius.com/images/default_avatar_300.png?1687811564"
    }
  ],
  "pageviews": "7132655",
  "isInTop10": false,
  "isArtistInTop10": false,
  "isAlbumInTop10": false,
  "isNewRelease": false,
  "isInTop10Rap": false,
  "isInTop10Rock": false,
  "isInTop10Country": false,
  "isInTop10RnB": false,
  "isInTop10Pop": false,
  "title": "​​rockstar",
  "primaryArtist": "Post Malone",
  "primaryArtistId": 326362,
  "createdAt": "2016-12-28T00:44:11Z",
  "songTier": "D",
  "releaseDate": "2017-09-15",
  "commentCount": 371,
  "isHot": false
}
```

## Contact 
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
