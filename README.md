# TryHackMe CTF Writeups

Benvenuti to my **CTF Writeups** repository! 

This repository contains detailed writeups for Capture The Flag (CTF) challenges on [TryHackMe](https://tryhackme.com) (and more websites to follow!). Each writeup is designed to document my learning process, methodologies, and solutions while solving various challenges.


## Website
You can find the website hosted at the following link: https://giabbi.github.io/ctf-writeups-THM/


## Repo Structure and Tech Stack
```bash
.
├── _writeups/         # Markdown writeups for each CTF challenge
├── _layouts/          # Jekyll HTML layout template (mainly for footer/header and CSS override)
├── assets/            # Images, CSS, and static resources
├── index.md           # Main landing page for the website
├── _config.yml        # Site configuration and metadata
└── README.md          # You're here!
```

As for the technologies used, here's my current stack:
- Jekyll – Static site generator with "Hacker" theme

- GitHub Pages – Hosting

- Markdown – All writeups are written in Markdown

- HTML/CSS tweaks for layout and styling


## Contributing
While this repository is primarily for my personal learning journey, contributions and suggestions are welcome and encouraged! If you'd like to share your own insights or point out improvements, feel free to open an issue or create a pull request.

To test my website on your local machine, follow these steps:

Make sure you have the latest version of ruby and bundler nstalled, if you are on linux then run:
```bash
sudo apt update
sudo apt install ruby-full
gem install bundler
```

After that, clone my repository and run this to install dependencies:
```bash
bundle install
```

Lastly, run the following command for a preview of the website that updates every time you make a change:
```bash
bundle exec jekyll serve --livereload
```

Now you can find the website at `http://localhost:4000/ctf-writeups-THM/`

## License
The writeups and content in this repository are licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

This means you're free to use, share, and remix the material for **non-commercial** purposes, as long as you:
- Provide proper **attribution**.
- Share any adapted material under the **same license**.

Reposting or monetizing my writeups without permission is strictly forbidden.
