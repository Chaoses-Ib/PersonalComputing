# [Zotero](https://www.zotero.org/)
[GitHub](https://github.com/zotero/zotero)

[Zotero 中文小组](https://zotero-chinese.com/)

## Installation
`scoop install zotero`
- [zotero: Added `zotero://` url protocol `post\_install` script by FlawlessCasual17 - Pull Request #10644 - ScoopInstaller/Extras](https://github.com/ScoopInstaller/Extras/pull/10644)

  The replaced script will be saved to `%USERPROFILE%\scoop\apps\zotero\current\install-zotero-url-protocol.ps1`. This is a bit confusing since there is no tip about it.

> Your computer must be restarted to complete a previous upgrade of Zotero. Do you want to reboot now?
- [Zotero update requires reboot (constantly) - Zotero Forums](https://forums.zotero.org/discussion/109234/zotero-update-requires-reboot-constantly)

## Data
Data (the same for installer and Scoop):
- `%USERPROFILE%\Zotero`
- `%APPDATA%\Zotero\Zotero\Profiles\123abcde.default`
- [Tara: A Zotero add-on for backup and restore preferences, add-ons, translators, styles, and locate between two machines](https://github.com/l0o0/tara)

[Zotero Database Repair Tool](https://www.zotero.org/utils/dbfix/)

### [Sync](https://www.zotero.org/support/sync)
- Data syncing
  - Full text indexes
- File syncing
  - [Zotero](https://www.zotero.org/storage)
    - Free: 300 MB
  - WebDAV (ZIP)
  - [Linked files](https://www.zotero.org/support/attaching_files#stored_files_and_linked_files) + file sync tools
  - Download files at sync time / as needed

> Storing the Zotero data directory directly in a cloud storage folder is [extremely likely to corrupt your Zotero database](https://www.zotero.org/support/kb/data_directory_in_cloud_storage_folder) and should not be done.

## History
### v7
[Announcing the Zotero 7 Beta - Zotero Forums](https://forums.zotero.org/discussion/105094/announcing-the-zotero-7-beta)

[Available for beta testing: Zotero, redesigned - Zotero Forums](https://forums.zotero.org/discussion/111074/available-for-beta-testing-zotero-redesigned)

New features:
- Dark mode

## Reader
[The Zotero PDF Reader and Note Editor](https://www.zotero.org/support/pdf_reader)

- Free
- Formats: PDF, EPUB, webpage snapshots

  [Available for beta testing: Updated reader with EPUB/snapshot support and new annotation types - Zotero Forums](https://forums.zotero.org/discussion/106716/available-for-beta-testing-updated-reader-with-epub-snapshot-support-and-new-annotation-types)
- Dark mode (v7)
- Autolinks for URLs and DOIs

  [Feature request: links in pdf document in reader should be clickable - Zotero Forums](https://forums.zotero.org/discussion/95485/feature-request-links-in-pdf-document-in-reader-should-be-clickable)

  But not for plain-text citations.

- Preview page when hovering links (citations)
- Internal annotations

  Annotations created in the built-in PDF reader are stored in the Zotero database, so they won't be visible in external PDF readers unless you export a PDF with embedded annotations. See [Annotations in Database](https://www.zotero.org/support/kb/annotations_in_database) for more info.

  - Image annotations
  - Timestamps: Only shown in tooltips

    [Annotation timestamps and impact on pdf date modified field - Zotero Forums](https://forums.zotero.org/discussion/105791/annotation-timestamps-and-impact-on-pdf-date-modified-field)

    [Zotero PDF annotation: Sort by date \[Feature request\] - Zotero Forums](https://forums.zotero.org/discussion/90762/zotero-pdf-annotation-sort-by-date-feature-request)

    [Feature Request: Expose Annotation Timestamps (Creation/Modification Date) via API for Plugin Use - Zotero Forums](https://forums.zotero.org/discussion/123405/feature-request-expose-annotation-timestamps-creation-modification-date-via-api-for-plugin-use)
  - Syncing
- "Open Documents" support when adding citations

## Add-ons
[plugins \[Zotero Documentation\]](https://www.zotero.org/support/plugins)

[Zotero 插件商店 - Zotero 中文社区](https://plugins.zotero-chinese.com)

- [Add-on Market for Zotero: Install add-ons directly in Zotero | Zotero插件市场](https://github.com/syt2/zotero-addons)
- [SciPDF For Zotero: Download PDF from Sci-Hub automatically For Zotero7](https://github.com/syt2/zotero-scipdf)

## Citation counts
- [Zotero Citation Counts Manager: Zotero plugin for auto-fetching citation counts from various sources](https://github.com/eschnett/zotero-citationcounts)
  - [Zotero 7 Citation Counts Manager Enhaned](https://github.com/FrLars21/ZoteroCitationCountsManager)
  - [Zotero-Literature-Manager: A plugin for Zotero to automatically retrieve citation, official code link, conference, related papers and so on.](https://github.com/AlbertShenC/Zotero-Literature-Manager)

- [Google Scholar Citation Count for Zotero](https://github.com/justinribeiro/zotero-google-scholar-citation-count)
  - [Zotero 7 Support - Issue #14 - justinribeiro/zotero-google-scholar-citation-count](https://github.com/justinribeiro/zotero-google-scholar-citation-count/issues/14)

[Citation count - Zotero Forums](https://forums.zotero.org/discussion/77638/citation-count)

## Citation styles
[Citation Styles](https://www.zotero.org/support/styles)

[Zotero Style Repository](https://www.zotero.org/styles)

[GB/T 7714 信息与文献　参考文献著录规则](https://zh.wikipedia.org/wiki/GB/T_7714)
- [GB/T 7714—2015 相关的 CSL 样式](https://github.com/redleafnew/Chinese-STD-GB-T-7714-related-csl)

## Editors
### VS Code
Extensions:
- [zotex: A VSCode Extension: Zotero with Better Bibtex support for LaTeX.](https://github.com/raykr/zotex)
  - Bibliography
  - [Open PDF in Zotero - Issue #11](https://github.com/raykr/zotex/issues/11)
  - Weird default key bindings: [Control + Z is blocked by Zotex - Issue #3](https://github.com/raykr/zotex/issues/3)
    - `Ctrl+Z`: Add Citation
    - `Ctrl+Alt+z`: Cite and Create Bibliography for LaTeX/Pandoc
    - Cite and Create Bibliography for Markdown
    - `Ctrl+S`: Add Zotero Selected Citation
    - `Ctrl+Alt+S`: Add Zotero Selected Citation and Bibliography
    - Open in Zotero
  - Recommanded key bindings
    - `Shift+Alt+Z`: Cite and Create Bibliography for Markdown
  - Activation time: 16ms

- [mblode/vscode-zotero: Zotero Better Bibtex citations for VS Code](https://github.com/mblode/vscode-zotero)
  - `Shift+Alt+Z`: Zotero Citation Picker
  - `Ctrl+Shift+Z`: Open in Zotero
  - `Ctrl+Shift+Alt+Z`: Open PDF from Zotero
  - Activation time: 1s

- [vscode-zoterolens: CodeLens extension for VSCode, providing quick access to Zotero information and attachments from citations. - Forgejo - Ruben van de Ven](https://git.rubenvandeven.com/r/vscode-zoterolens)
  - Scan works, but not open

  ```ts
  [error] TypeError: Cannot read properties of null (reading 'toString')
      at IncomingMessage.<anonymous> (c:\Users\Chaoses\.vscode\extensions\rubenvandeven.zoterolens-0.2.1\out\commands.js:55:34)
      at IncomingMessage.emit (node:events:519:28)
      at emitReadable_ (node:internal/streams/readable:832:12)
      at onEofChunk (node:internal/streams/readable:810:5)
      at readableAddChunkPushByteMode (node:internal/streams/readable:464:5)
      at IncomingMessage.Readable.push (node:internal/streams/readable:390:5)
      at HTTPParser.parserOnMessageComplete (node:_http_common:152:12)
      at Socket.socketOnEnd (node:_http_client:527:12)
      at Socket.emit (node:events:531:35)
      at endReadableNT (node:internal/streams/readable:1696:12)
      at processTicksAndRejections (node:internal/process/task_queues:82:21)
  ```

- [ZhiguoLong/vscode-zotero-backward-searcher: Support inserting citations from Zotero and open citation in Zotero (backwardsearch).](https://github.com/ZhiguoLong/vscode-zotero-backward-searcher) (discontinued)

Test: @vaswaniAttentionAllYou2017a
