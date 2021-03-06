
# Resume - Details

## Courses

* Advanced Data Structure
    - Revision of B.Tech material with a focus on proofs
        + Graphs
    - Heaps
        + Binomial Heap
    - Amortized Analysis
    - Quick Sort & Family
    - Greedy framework
        + Matroid Theory
    - Union Find
    - Skip Lists
    - KD Trees
    - Convex Hulls
    - NP Completeness & Reductions

* Introduction to Logic & Functional Programming
    - Abstract mathematics
    - Ocaml - functional paradigm
        + Recursive structures - trees etc.
        + `map, fold`
        + Pattern matching
    - Assignments
        + Representing sets with list
        + Propositional logic and conversions
        + Proof trees & natural deduction

* High Speed Networks
    - Digital cash
    - Cryptography Basics
    - Blocks
        + Merkle tree
    - Possion processes
    - Attacks on Blockchains
        + 51%
        + Arbitrary Target
        + Block Discarding
        + Slefish Mining
    - Smart Contracts
    - Limitations of Bitcoin
    - Proof Of Stake
        + Problems

    - Fruitchain
    - Bitcoin NG

    - Consensus
        + Proof of Work
        + Paxos, RAFT
        + PBFT & Byzantine Fault Tolerance
        + Zyzzyva

    - Hyperledger Fabric
    - Algorand

    - Lightning Networks
        + Bitcoin scalability
    - Truebit & Compute intensive smart contracts

* Network & System Security
    - Stream Ciphers
        + RC4, LFSR

    - Block ciphers
        + DES
        + AES

    - Public-key cryptography:
        + Diffie Hellman
        + RSA
        + ElGamal
        + Elliptic Curves

    - Hash functions
        + MD5
        + SHA 1, 2
        
    - Message Authentication Codes
    - Digital signatures

    - Key management
        + PKI and Certification

    - Applications to network security:
        + Wi-Fi security
        + Kerberos-based authentication
        + VPN, or IPSEC
        + Transport-layer authentication
        + Email systems


## Work Experience

### Adobe

* I was on the QA team behind Adobe Create Cloud Bootstrapper
    - The application that installs other Adobe creative cloud apps
    - Adobe CCX - Codenamed Thor
    
* The Bootstrapper was written using web technologies
    - Running in a chrome instance
    - We used to perform automated black-box testing
        + Primarily using Python & Selenium
        
* I individually worked on two modules

    - Automating the testing of files web UI

        + Had two parts
            * Interfacing with the Web UI
            * Interfacing with Thor's UI

        + Testing whether files were being synced properly
            * Add file to local folder & check on Web UI
            * Remove local files & check again

    - Extracting performance data from log files

        + Launch CCX and gather metrics from log file
            * Load complete, Sign In, Panel loads etc.

        + The module existed before but it didn't capture a lot of details

            * So I re-wrote it from scratch
                - It was making multiple passes over the log file
                - It used split on space & list indexing
                    + While I replaced it with regex

            * Gathered Download/Extract/Install timing
                - Size, Time, Speed etc.

## Internships

### GSoC 2016 - mitmproxy

* __TODO: How do proxies work?__
    - What in the HTTP protocol allows it?
    - Keys installed by mitm

* mitmproxy is an HTTP proxy tool 
    - programmable via Python

    - can do things like
        + view all API calls that a particular android app makes
        + upside down all images

    - similar to
        + browser networks tab
        + Fiddler / Charles / Burp suite

* Components

    - pathod
        + Can generate HTTP responses with certain properties
        + Including those that violate standards

    - pathoc
        + Generate arbitrary requests
        + Can be used to fuzz test HTTP servers

    - netlib

* Majority part was on porting the project from Python 2 to 3

    - The plan was to first make it compatible with both Python 2 & 3
        + using the 'six' package
        + and then later drop support for Python 2
        + All core dependenices were already Python 3 compatible
        + Port requires good test coverage (> 90%)

    - 2 vs 3 Differences
        + Syntax: print function etc. (2to3!)

        + String to Bytes / Unicode difference was the biggest change
            * Mostly just adding an encode()/decode() pair at the right position
            * Py2: str / unicode
            * Py3: bytes / str

        + IDNA Host encoding
            * punycode

* Export flows
    - As Curl command / Python code etc.
    - or as a HAR file

* Console client improvements

    - TCP Flow & filters

    - Marked property & filters
        + Each flow has a marked property

* Parse comma separated cookie
    - Set-Cookie with comma separated values
    - To set multiple cookies

### GSoC 2015 - CritiqueBrainz

* Website for reviewing music albums, events etc.
    - Webservice / API too
    - Written in Python / Flask

* Database / Schema
    - When I did the project, we used an ORM for interfacing - SQLAlchemy
    - But later the project moved on to raw SQL queries

* Improved test coverage
    - API / Frontend tests
        + Post & Assert

* Moderation UI & Log
    - Users report (SpamReport table)
    - Moderators take action
        + Actions are also logged (ModerationLog table)
        + Block a user, Delete review etc.
    - Admin views weren't used because we wanted minimal UI
        + So users don't get confused

* Revision history
    - List old revisions - Pagination
    - Can view diff of past revisions
        + Side by side diff - difflib
    - Revisions table

* Review other entities
    - Like events & places etc.
    - Previously only albums could be reviewed
    - Leaflet map on events - interfaced with OSM API

### GSoC 2014 - Picard

* MusicBrainz is an organization that deals with curation of music related data
    - and then makes it available for the world

* Picard is a tool that tags MP3 files
    - ID3 tags
    - Fetches data from 

* Created a simple landing website
    - Python / Flask / Jinja / Bootstrap
    - Platform specific download button
    - List of plugins
    - Parsed changelog file and displayed neat UI

* Web API
    - Users submit their plugins to a Github repo
        + From where the list is fetched & displayed
    - List available plugins (from a local JSON file)
    - Allow downloading of plugin zips

* Integrate API with the tool
    - Written in Python / PyQt4
    - Download JSON from the API
    - Match with already existing plugins
    - Added a TreeWidget with data

## Projects

### Major Project: Bitcoin

* New approach to Blockchain stability
    - Anchors
    - Patent, NDA
    - __TODO: Read Ovia's Patent Document__

* Modifications to the bitcoin core

    - Similar to Bitcoin NG & Fruitchain?
        + A new type of block

    - Added a vector of children of a block
        + To update nChainWork in forward direction
        + via a BFS
        + Only had parent pointers before

    - Anchor
        + New message type
        + Has no txns
        + Stored in a map (to prevent duplicates)
        + Updates nChainWork on receipt
        + generateanchor, submitanchor commands
        + Forwarded to peers via Broadcast

* Testbed to run simulations

    - Involving multiple bitcoin nodes

    - Cluster of 3 virtual machines
        + Each of which running 50 bitcoin daemons

    - __TODO: Class Diagram__
        + Node
        + Network
        + Master

### Minor Project: Accelphone

* Report Outline

    - Introduction
        + Goal
        + MEMS Accelerometer
            * __TODO: Working of Sensors__
            * Sensing mass suspended with springs
            * Gets displaced due to forces
                - which could be acoustic vibrations

        + Human audible frequencies
            * 20Hz to 20kHz

        + Sensors on an Android Phone
            * Rate limited by the Kernel: 200Hz
            * Explored changing the kernel itself?
                - but user phones won't have that kernel
            * Raise no alarm - permission popup

        + Recent update in Android Pie

    - Literature

        + Gyrophone
            * Rate limited data
            * ML: SVM etc.
                - Speaker, Gender Identification
            * Multiple phones

        + Walnut Attack
            * Requires resonant frequencies
            * Can completely control the sensor

        + PIN Attack
            * Figure out which key was pressed by 
            * No acoustics
            * Touch events on screen
            * Followed by ML: KNN, GNB, MLP, RF
            * Found that combination of sensors work best
    
    - Exploit in Browsers
        + Chrome rate limits: 60Hz
        + Firefox is still: 200Hz

    - Sensor Tile Kit
        + ST Microelectronics
            * Promises an accelerometer with 6000Hz rate

        + Most of the time on the project was spent here?

        + Couldn't succeed in gathering data 
            * At maximum rate
        + Recording both sensor & microphone failed

    - Android App
        + Limited data rate: 200Hz
        + Stored all data

            * Sensors: `timestamp, x, y, z`
                - `import android.hardware.Sensor`
                - `SensorManager, Sensor.TYPE_ACCELEROMETER`
                - `registerListener, SensorEventListener, onSensorChanged`
                - `SENSOR_DELAY_FASTEST`

            * Audio: M4A
                - `import android.media.MediaRecorder`
                - `Source: MIC, OutputFormat: MPEG_4, AudioEncoder: AAC`

    - Experiment
        + Let the android application run in background
        + Then use a beeper application, connected to a speaker
            * To generate single frequency tones
        + Noise
            * Should've been done in an anachronic chamber? 

    - Analysis
        + Convert M4A to WAV
            * via FFMpeg
            * Read using `scipy.wavfile`

        + Plots
            * Time-Amplitude
                - The normal plot usually associated with sound waves?

            * Frequency-Amplitude
                - Found via FFT
                - Break a wave into its individual frequency components
                    + To find if there is a single freq tone

            * Time-Frequency

        + Modules
            * numpy, pandas, matplotlib
            * scipy: fftpack, signal, wavfile

* __TODO: Signal processing concepts__
    - Nyquist sampling
    - Aliasing effects
    - Fast Fourier Transform

### Discrete-event Blockchain simulator 

* Wrote a simulator (in Python) 
    - Modules used?

* Showing effects 

* Various starting parameters 
    - Which parameters?

* Can have on a Blockchain's growth.

---

* Simulator
    - Central dispatch

    - Priority queue of events
        + prioritized by scheduled time
        + `queue.PriorityQueue`

    - 4 types of events: 
        + Transaction Generate
        + Transaction Receiveeive
        + Block Generate
        + Block Receive

        + Each of them has different run-semantics
        + Corresponding event is queued at other node

    - Seed events
        + 1 TxGen, BlkGen per node

    - Simulation is potentially infinite
        + Limit on number of events

    - At the end
        + Dump blockchain in DOT lang
        + Tool to convert DOT to 

* Network
    - Slow & Fast network
    - Low CPU, High CPU ?
    - Latency between nodes
        + Propagation delay 

    - Each node connected to random no. of nodes
        + But still the graph is connected

* Parameters
    - Number of nodes (n)
    - Fraction slow (z)
    - Txn inter-arrival mean (Tm)
    - Block inter-arrival mean (Bm)

* Effects

__TODO: Read Report!__

* Reason for choosing exponential distribution for inter-arrival between
transactions
    - __TODO: Exponential & Poisson Distributions__

### Ethereum Smart Contract

* Problem
    - Parties
        + Creator
        + Smart Contract
        + Consumer

    - Creator can add their media entries to the Contract
    - Consumers can buy them
        + By paying money & receiving an encrypted URL
        + Encryption can't happen on chain
            * Was done in JS tests
            * Data transfer via Events

* Stack

    - Solidity 
        + for the core smart contract code.

    - Ganache 
        + to run a local Ethereum testnet. 
        + I used the GUI, but `ganache-cli` will work as well.

    - Truffle
        + to manage the dev environment
        + compile contract, interact with local testnet and run tests.
        + `solc`: solidity C++ to Javascript via `Emscripten`

    - Solium
        + to lint the contract for style and security best practices.

    - ES6 - Mocha & Chai
        + for writing unit tests.

    - ES Lint
        + for linting the JS tests.

* `contract MediaMarket`
    - `struct Media`
        + id, name, creator, cost
    - `mapping media_store`
    - `mapping purchases`

    - `add_media`
    - `buy_media`
        + payable
        + generates `evConsumerWantsToBuy`
        
    - `url_for_media`
        + generates `evURLForMedia`

* Tests
    - Used `chai` to write tests
        + assert, isEqual, isRejected etc.
    - Smart contract becomes a JS object

* __TODO: Read Ethereum Solidity docs__
    - Core concepts:
        + Gas used
        + Data types
        + Where is the data stored etc.

    - JS Concepts
        + Async functions, Promises etc.

### Anonymity Term paper 

* Introduction
    - Traditional banking system
        + Private
        + Centralised trust

    - Bitcoin: Distributed Ledger
        + Public
        + Decentralised trust
        
* De-anonymizing Bitcoin
    - Bitcoin paper - privacy section
    - Pseudonymous identities - addresses
    - Change addresses

    - Transaction graph analysis
    - Web crawling - side channel
    - Network traffic analysis
    - Tracking payments
    - Blockchain surveillance industry

* Proposed Solutions
    - Done in group of 3!

    - CoinJoin
    - JoinMarket
    - Mixing services
        + External anonymity but partial internal
        + May not even return money back

    - TumbleBit
        + No trust mixer
        + Compatible with Bitcoin

    - ZCash
        + Zero knowledge proofs
        + Txns encrypted - privy only to the involved parties
        + Transparent & Shielded addresses
        + Note - Commitment - Nullifier

        + Trusted setup phase
            * Multi party computation

        + Shielded Txns are computationally expensive
        + Reduced scalability?

    - MimbleWimble

### P2P cryptocurrency simulator 

* Problem
    - Implement a DHT to store keypairs - (node ip, port)
    - Two phase commit protocol to do Txn
    - Sender broadcasts committed Txns
    - Receiver verifies the signatures 
    - Concurrent Txns - same order - virtual synchrony
    - Prevent double spends

* Modules
    - Kademlia Node
    - Routing Table
    - Datagram RPC Protocol

    - Node
    - Ledger
    - Transaction

    - Python
        + asyncio
        + aioconsole
        + shlex
        + sockets
        + hashlib
        + ecdsa
        + logging

* Mininet
    - start_network
    - cleanup
    - Runs hosts

* Concurrency
    - `asyncio` event loops

* Distributed Hash Table
    - RPC over UDP

    - Kademlia Protocol

        + ping
        + store: key, value
        + find_node: key
            * Return: K closest peers to a key
        + find_value: key
            * Return: value of the key 
            * OR: K-closest peers

        + put: key, value
            * Return: No. of nodes who stored
        + get: key
            * Return: value

        + lookup_node

        + ping_all_neighbours
        + join:
            * Performed by new joining node

        + broadcast

    - Routing Table
        + buckets
            * max k peers per bucket
            * stored on the basis of last interaction
        + update_peer
        + remove_peer
        + find_closest_peers

* Simulated a P2P cryptocurrency network 

* Nodes could perform transactions
    - Happens via Two phase commit

* __TODO: Read the document__
    - How does Kademlia work?
    - How do Txns happen?
    - Why couldn't we handle concurrent ones?
    - Double spends?

### Analysis of GitHub data

* Stack
    - HDFS
        + To store data

    - Spark
        + To perform analysis

    - Jupyter Notebooks
        + As the means of running queries

    - Plotting
        + d3.js
        + bokeh
        + matplotlib

* Installation of HDFS & Spark
    - Various issues on the cluster
    - First we were trying out MapReduce / YARN but we couldn't set it up
    - Then Harish setup standalone Spark on his laptop
    - Once that worked, we did it on Baadal as well
    - YARN wasn't required - Spark handled it all

* Dataset: GHTorrent
    - 60 GB compressed - 225 GB uncompressed
    - 20 CSV files

    - We did analysis on 9 files
        + 94 GB

    - Preprocessing
        + xsv tool to remove columns we weren't interested in
        + We did this locally
            * Only because we didn't have permanent access to Baadal
            * So we shortened it first and then uploaded (via LAN etc.)
        + After preprocessing: 55 GB

* Analysis
    - Users: 20 million
    - Exponential growth
        + from 2008 to 2017
        + `users.select(F.year('created_at').alias('year')).groupBy(year).count()`
        + `SELECT COUNT(*) FROM USERS GROUP BY YEAR('created_at')`
    - New users per year-month
        + `GROUP BY YEAR('created_at'), MONTH('created_at')`
    - User distribution
        + Global, India
        + `GROUP BY 'country_code'`
    - Organizations
        + Global, Indian
        + Parameters
            * Number of employees
            * Followers per employee
            * Stars per employee
    - Users at IITs
        + `company.name.startswith("IIT | INDIAN").groupBy('company').count()`
    - Activities
        + Commit patterns of users
            * Number of comits - Time of day vs Day of Week
            * People had varying punchcards - some work in day / night etc.
        + Community participation
            * No. of projects vs % Community participation
                - Normal curve
            * `SELECT ceiling(100 * commits_by_others / total_commits) as community_part, COUNT(*) as num_repos GROUP BY project_id`
            * Most had 0%
                - Showed bus factor - 1
        + Programming language popularity
            * by Code size!
                - Lame metric
                - We were trying to see if Java will come on top
                     * Because it is verbose
                     * But, C came on top, followed by JS, Java, PHP, Python, Ruby
            * `project_languages` table

* __TODO: List all queries__
    - Schema of the tables
        + Users, Followers, Projects, Stars, 
        + Project Language, Project Members, 
        + Commits, Issues, Pull Requests
    - Larger queries run

### Machine Learning Algorithms

* Regression
* Naive Bayes
* SVM (Pegasos)
* Decision Trees

### Network Security Algorithms

* Data Encryption Standard
    - Initial Permutation
    - 16 Rounds of feistel
    - Key Schedule / Expansion for round keys
    - Feistel
        + Permute
        + XOR
        + Substitute
        + Permute

* Rivest Shamir Adleman
    - Generate Key Pair
        + `n, p, q, phi`
    - Encrypt / Decrypt

* Document time-stamping authority
    - Calculate file hash
    - Send to TSA
    - Append timestamp
    - Encrypt with TSA's private key
    - Now, it can be verified by anyone having TSA's public key

* Certification authority
    - Clients communicate with CA to get certificate
    - Clients can then talk to each other

    - CA needs to be trusted by both
        + and they should have hardcoded its key
        + Browsers do this too!

### Open Source - GitHub projects

#### Contributed a patch to youtube-dl

* youtube-dl
    - 45k stars on GitHub
    - 16k commits
    - 1000+ sites supported (not just Youtube)
    - written in Python

* Architecture
    - extractors
        + ABC: `InfoExtractor`
            * Read pages: HTML, XML, JSON
            * Parse high level details?
        + Extractor per site
            * Single video
            * Playlist

    - downloaders
        + ABC: `FileDownloader`
            * deals with progress bar etc.
        + External tools
            * Curl, Wget, Axel, Aria2
        + HTTP, HLS, DASH etc.

    - postprocessors
        + FFMpeg 
            * Convert to MP3, Add metadata etc.

* WebOfStories
    - In June 2015
    - To Download the Donald Knuth playlist

* WebOfStoriesExtractor
    - Regex to match URL with
    - Extract bits of information
        + Speaker ID, Story name etc.
    - Build URL
    - Return a dictionary
        + All formats with URLs

    - Tests
        + Run extractor on a URL 
        + Match with hardcoded dict of values

#### Sublime Text Plugins

* kemayo/sublime-text-2-goto-documentation
    - [AHK Support](https://github.com/kemayo/sublime-text-2-goto-documentation/pull/27)

* Sublimall - Sync settings across machines
    - [Find 7zip in Program Files etc.](https://github.com/toxinu/Sublimall/pull/15)
    - [Misc. fixes](https://github.com/toxinu/Sublimall/pull/21)

* GitHubinator - Copy GitHub links to files / lines
    - [Quote URL before copying it to clipboard](https://github.com/ehamiter/GitHubinator/pull/57)
    - [BitBucket Support](https://github.com/ehamiter/GitHubinator/pull/33)
        + `get_selected_line_nums`
        + `get_git_status`
        + Find git remote URL by reading config file
        + Use BitBucket / GitHub specific URLs

*  alecthomas/SublimeFoldPythonDocstrings
    - [Support MagicPython Syntax](https://github.com/alecthomas/SublimeFoldPythonDocstrings/pull/6/)

* Default Sublime packages
    - [Comment character for batch Files](https://github.com/sublimehq/Packages/pull/45)

* Git: Region history
    - Git log selected lines of a file
    - Only shows commits that touched those lines

* Jrnl
    - List journals stored on disk
    - Add a quick note to the Jrnl

* Session file fixer
    - Cleans up the project switcher list
    - Remove entries to non-existent paths

* Lexicon
    - Display word definition in a popup
        + along with 5 synonyms of the word
        + and an external link

    - Uses datamuse API
    - Needs to be made async

* KDE Dialogs
    - Open KDE Dialogs instead of GNOME ones
    - Open file, folder, save etc.

#### massren: Batch renaming of files

* Used to be a Go tool
    - Re-wrote in Python

* Opens up the editor with a list of files
    - Allows you to use all your editor shortcuts / plugins
    - Saving & closing the file performs renames

    - Can comment a line to delete the file

* Todo
    - See what conflicts could occur and warn
        + while leaving the file on disk
        + so that it can be reopened and edited
    - Perform delete operations first

#### shotahk: Capturing & Uploading screenshots

* Written in AutoHotkey
    - circa 2012
    - 800 SLOC

* Ran in background
    - Could grab entire screen, area etc.
    - Used irfanview to actually capture the screenshot
        + with all effects

* Had a configuration GUI
    - Saved / loaded settings to the Windows registry

    - Save File
        + Path, name, extension
        + Prefix / Suffix

    - ScreenShot Action
        + Hotkeys

    - Effects
        + Grayscale, Resize, Rotate

#### pocketmon: Tagging my articles-to-read list

* Add reading time tags to each article on Pocket

* Use Pocket API to fetch articles
    - with their word count
    - calculate time reuired to read
        + with a speed of 250 words per minute
    - round off the time to nearest five
    - Send a request to `add_tag`

#### netuse: Monitoring my internet bandwidth consumption

* Written at a time when I used to live on MTS Dongle
    - 7 GBs per month quota (700 Rs per month)
    - 10 when I wanted to have fun! (1000 per month)
    - 20 GBs when MTS had some offer etc.

* Dumper CRON job
    - Ran every 1 or 2 seconds
    - Read data from `/sys/class/net/wlp2s0/statistics/{rx,tx}_bytes`
    - and dump to a file
        + in folder: `~/.net/.net/$year/$month/down/$date`
    - along with timestamp

* Analysis script
    - Read data from folder
    - and display aggregate information
        + per hour, day, week, month

    - Took monthly quota as input
        + along with last recharge date
        + To display data left
        + and suggested daily usage

* Notification
    - via CRON
    - Last hour's usage
    - and Suggested daily usage
        + taking monthly quota into consideration

#### topdf: Converting source-code/websites to PDFs

* I like PDFs for multiple reasons
    - Can be consumed offline
    - You can be sure of how they'll look
    - on iPad: support annotations

* **Geeks for Geeks**
    - Created at a time when the offline nature mattered a lot
        + Didn't want to have my laptop open
        + Didn't have WiFi / Mobile Data either
        + So used to put PDFs on phone
            * and practice on Notebooks

    - `list_links` 
        + from a topic URL
        + Generates a JSON
            * which can be cleaned & sorted

    - `download_html`
        + takes in the JSON
        + uses `requests_cache`
        + fetches HTML and cleans it
            * `lxml.cleaner`
                - scripts, comments, styles, forms 
            * XPATHs
                - class, ID, h1, h2, h3 etc.
                - Links / Paragraphs containing text
            * Convert code table to single pre tag

    - `html_to_pdf`
        + Pandoc with a custom template
        + Fixing weird errors

* **Source Code: Bitcoin, Python - requests, flask**
    
    - Wanted to experiment with reading code as prose
        + on my iPad

        + Get a bird's eye view on the source
            * Mark interesting points

        + Didn't really work out?

    - src2tex
        + Walks through a directory tree
        + Generating a .tex file (from a template)
        + With `\inputminted{}` entries per file
            * according to the type (language)

    - The .tex file can then be edited by hand 
        + Removing any spurious entries etc.
        + And then converted to PDF

* **topdf: Websites etc.**

    - Wanted a single entry point for all PDF conversion tasks

    - Modeled after youtube-dl
        + `path_handlers`
            * ABC: `Handler`
                - `can_handle`
                - `make_pdf`

            * Generic URL
            * GitHub Readme
            * Local file
    
            * Reddit
            * Stack Overflow
                - Use API to fetch markdown 
                - and then run Pandoc

        + `pdf_engines`
            * Libreoffice
            * Pandoc
                - Which inturn uses `xelatex` etc.
            * wkhtmltopdf ?

    - On receiving 
        
    - Did some research on existing PDF engines
        + their pros / cons

        + CutyCapt
        + QtWebkit
            * Potential to remove ads?!
        + MSOffice
        + NodeMarkdown
        + Gimli

#### 0xmirror: Creating a "zero-byte" disk mirror

* Walk source directory
    - Touch empty file at destination
    - Keep modification times intact

    - The plan was to run tar/7zip as a second pass
    - And run this as a CRON job

* Instead, started using the Unix `tree` command
    - to dump JSON
    - and then upload the JSON to dropbox etc.

#### cyril: Fetching & embedding lyrics into MP3 files

* Main source was inspired from Clementine
    - Was in C++

* Modules
    - `docopt`
    - `mutagen`
        + For MP3/ID3 reading etc.

* Modeled around youtube-dl
    - `providers`
        + ABC: `LyricsProvider`
        + Site specific HTML scrapers
            * `lxml.cleaner`
            * XPATH based tag text extraction

* Unit tests
    - Multipl tests per site
    - Compare with hardcoded files 
        + that the lyrics exactly matched

#### pdf-titles: Renaming research papers with their titles etc.

* Python script uses `kmetadump`
    - to find the title and rename pdf files

* Extraction of titles
    - Heuristics!

    - Find all textboxes and combine them based on height
    - Pick text in largest text boxes

    - Haven't been able to do this in Python
        + mostly because of the lack of a decent low level PDF library
        + Original code used Poppler
        + I couldn't work out how

## Talks

### Designing command-line interfaces in Python

* No such thing as a one-off script

* Many components of a CLI tool
    - Argument Parsing
    - Input
        + Interactive
        + Stream based
    - Output
        + stdout/stderr
        + Colors
        + Progressbar
    - Documentation
        + Manpage

* Discussed only argument parsing

* `argparse`
    - In python stdlib
    - Bit verbose

* `docopt`
    - Uses docstrings
        + Parses them to build a dictionary
    - Simple entrypoint - docopt.docopt()
    - Works in other languages as well

* In 2018, I'd probably use `click` now
    - because it has lots more stuff too
