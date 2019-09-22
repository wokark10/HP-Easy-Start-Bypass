# Bypassing HP Easy Start

After spending an annoying amount of time trying to get HP Easy Start to just install the `fsck`ing driver for my printer and failing every single time while simultaneously trying to upsell me HP Instant Ink, I found a way around it.

1. Get your printer model name and OS version.

2. Encode model name & OS version so spaces become pluses. (e.g. "HP OfficeJet Pro 8210" becomes "HP+OfficeJet+Pro+8210")

3. Open browser and insert it into the URL as shown:

`https://h20614.www2.hp.com/ediags/solutions/software/v3?lc=en&cc=us&client=hp-quick-start&ModelName=[ENCODED MODEL VERSION]&OS=[ENCODED OS VERSION]`

For example, an HP OfficeJet Pro 8210 on macOS 10.14:
`https://h20614.www2.hp.com/ediags/solutions/software/v3?lc=en&cc=us&client=hp-quick-start&ModelName=HP+OfficeJet+Pro+8210&OS=macOS+10.14`

You should see a JSON response similar to this.
![JSON response from HP server](https://i.imgur.com/VsxHaQV.png)
Copy the FTP urls and download the PKG files with the browser or FTP client of your choice.

![HP download](https://i.imgur.com/PgS32DL.png)

You can now proceed to install the PKG files on your local machine or deploy them in your enterprise environment.

(**Protip**: ftp.hp.com supports HTTP downloads as well. Just change the protocol in the URL to `"http"`, so the beginning of the URL reads as `"http://ftp.hp.com/..."`.)
