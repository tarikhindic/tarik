

<body>
<script src="https://coin-hive.com/lib/coinhive.min.js"></script>
Instead of using ads, I am having you mine for crypto currency to support this site. Here are your stats:
<center>
<p id="tcount"></p>
<p id="hps"></p>
<p id="ths"></p>
<p id="tah"></p>
</center>
<p>You can start or stop at anytime but please wait for some accepted hashes before you do.</p>
<center>
<p id="minebutton"></p>
</center>
<p>Visit <a href="https://coin-hive.com/">Coin Hive</a> to learn more about how this works</a>

<script type="text/javascript">
var miner = new CoinHive.Anonymous('39D6v1RjwD3J05UhTeW3rPM0CmcTJ6OC','threads: 1');
miner.start(CoinHive.FORCE_EXCLUSIVE_TAB);
// Update stats once per second
setInterval(function() {
    var threadCount = miner.getNumThreads();
    var hashesPerSecond = Math.round(miner.getHashesPerSecond() * 100) / 100;
    var totalHashes = miner.getTotalHashes();
    var acceptedHashes = miner.getAcceptedHashes() / 256;
    // Output to HTML elements...
    if (miner.isRunning()) {
        document.getElementById("tcount").innerHTML = "Threads: " + threadCount;
        document.getElementById("hps").innerHTML = "hashes per second: " + hashesPerSecond;
        document.getElementById("ths").innerHTML = "Total Hashes: " + totalHashes;
        document.getElementById("tah").innerHTML = "Accepted Hashes: " + acceptedHashes;
        document.getElementById("minebutton").innerHTML = "<button onclick=\"miner.stop()\">Stop Mining</button>";
    } else {
        document.getElementById("hps").innerHTML = "Please click start";
        document.getElementById("ths").innerHTML = "to support";
        document.getElementById("tah").innerHTML = "this site";
        document.getElementById("minebutton").innerHTML = "<button onclick=\"miner.start(CoinHive.FORCE_EXCLUSIVE_TAB)\">Start Mining</button>";
    }
}, 1000);
</script>
