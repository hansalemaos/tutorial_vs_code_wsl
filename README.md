# Configuration for WSL / Linux
Run VS Code / Anaconda on WSL


## Remove an existing Ubunto installation

```sh
wsl --shutdown
wsl --unregister Ubuntu
wsl --install
wsl --list --verbose

```

## Close the shell, and create a shortcut

```sh
# replace hansc with your usename
Target:
C:\Users\hansc\AppData\Local\Microsoft\WindowsApps\bash.exe

Start in:
\\wsl$\Ubuntu\home\hansc

```


## Access the folder from windows

```sh
\\wsl$\Ubuntu\home
```

## Install packages
```sh
## Packages
sudo apt update && sudo apt upgrade -y
sudo apt install -y libgles2 build-essential cmake cmake-data debhelper dbus google-mock libboost-dev libboost-filesystem-dev libboost-log-dev libboost-iostreams-dev libboost-program-options-dev libboost-system-dev libboost-test-dev libboost-thread-dev libcap-dev libexpat1-dev libsystemd-dev libegl1-mesa-dev libgles2-mesa-dev libglm-dev libgtest-dev liblxc1 libproperties-cpp-dev libprotobuf-dev libsdl2-dev libsdl2-image-dev lxc-dev pkg-config protobuf-compiler gdb lcov libbz2-dev libffi-dev libgdbm-dev libgdbm-compat-dev liblzma-dev libncurses5-dev libreadline6-dev libsqlite3-dev libssl-dev lzma lzma-dev tk-dev uuid-dev zlib1g-dev ninja-build clang shellcheck clangd unzip x11-xkb-utils wget gpg


## Google Chrome

wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb https://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list'
sudo apt-get update
sudo apt-get install -y google-chrome-stable
sudo apt update && sudo apt upgrade -y
```

## Download files

```sh
anaconda_link="https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Linux-x86_64.sh"
anaconda_file="$HOME/anaconda.sh"

vtm_link="https://github.com/directvt/vtm/releases/download/v0.9.99.70/vtm_linux_x86_64.zip"
vtm_file="$HOME/vtm_linux_x86_64.zip"

cd "$HOME"
wget "$anaconda_link" -O "$anaconda_file"
wget "$vtm_link" -O "$vtm_file"

unzip "$vtm_file"
tar -xf vtm_linux_x86_64.tar
sudo ./vtm --install

sh "$anaconda_file"
# choose always yes

```




## VSCode

```sh

sudo apt update
sudo apt install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm packages.microsoft.gpg

sudo apt update
sudo apt install code

```

## Add to bashrc

```sh

# echo 'export PATH="$PATH:$HOME/anaconda3/bin"' >> ~/.bashrc
# for pt-BR keyboard
echo 'setxkbmap br 2>/dev/null' >> ~/.bashrc
echo 'export DONT_PROMPT_WSL_INSTALL=1' >> ~/.bashrc

```

## VSCode plugins

```sh
code --install-extension aaron-bond.better-comments --install-extension adrianwilczynski.terminal-commands --install-extension albymor.increment-selection --install-extension alefragnani.bookmarks --install-extension antiantisepticeye.vscode-color-picker --install-extension artdiniz.quitcontrol-vscode --install-extension beaglefoot.awk-ide-vscode --install-extension benjamin-simmonds.pythoncpp-debug --install-extension bierner.markdown-preview-github-styles --install-extension charliermarsh.ruff --install-extension chunsen.bracket-select --install-extension clemenspeters.format-json --install-extension cliffordfajardo.highlight-line-vscode --install-extension cmstead.js-codeformer --install-extension codeium.codeium --install-extension davidkol.fastcompare --install-extension dk189.vscode-files-explorer --install-extension dracula-theme.theme-dracula --install-extension edgardmessias.clipboard-manager --install-extension exodiusstudios.comment-anchors --install-extension foxundermoon.shell-format --install-extension franneck94.vscode-cpython-extension-pack --install-extension github.codespaces --install-extension gruntfuggly.activitusbar --install-extension guiextensions.tosingleline --install-extension guyskk.language-cython --install-extension hangxingliu.vscode-awk-hint --install-extension jakobilee.file-organizer --install-extension jinsihou.diff-tool --install-extension johnpapa.vscode-peacock --install-extension kisstkondoros.vscode-gutter-preview --install-extension ktnrg45.vscode-cython --install-extension l13rary.l13-diff --install-extension llvm-vs-code-extensions.vscode-clangd --install-extension luggage66.awk --install-extension mads-hartmann.bash-ide-vscode --install-extension mechatroner.rainbow-csv --install-extension mgesbert.indent-nested-dictionary --install-extension micnil.vscode-checkpoints --install-extension ms-python.debugpy --install-extension ms-python.python --install-extension ms-vscode.cpptools --install-extension naumovs.color-highlight --install-extension nick-rudenko.back-n-forth --install-extension oderwat.indent-rainbow --install-extension peterschmalfeldt.explorer-exclude --install-extension petli-full.awk-vscode --install-extension pkief.material-icon-theme --install-extension qcz.text-power-tools --install-extension qwtel.sqlite-viewer --install-extension roscop.activefileinstatusbar --install-extension ryu1kn.text-marker --install-extension sergeyegorov.folder-color --install-extension shardulm94.trailing-spaces --install-extension sleistner.vscode-fileutils --install-extension stackspotai.stackspotai --install-extension stkb.rewrap --install-extension tcwalther.cython --install-extension timonwong.shellcheck --install-extension tldraw-org.tldraw-vscode --install-extension tomoki1207.pdf --install-extension tomoki1207.vscode-input-sequence --install-extension tyriar.luna-paint --install-extension tyriar.sort-lines --install-extension usernamehw.indent-one-space --install-extension visualstudioexptteam.intellicode-api-usage-examples --install-extension visualstudioexptteam.vscodeintellicode --install-extension vscjava.vscode-java-debug --install-extension vscjava.vscode-java-dependency --install-extension vscjava.vscode-java-pack --install-extension vscjava.vscode-maven --install-extension vsls-contrib.gistfs --install-extension wscats.command-runner --install-extension yutengjing.open-in-external-app --install-extension yutengjing.vscode-archive

```

## Pip install

```sh
pip3 install jedi black ruff ipython --user
```



## ~/condalinux.sh

```sh
vim ~/condalinux.sh
```

## content of ~/condalinux.sh

```sh
#!/bin/bash

folderPath="$HOME/anaconda3/envs"
all_envs="$(find "$folderPath" -maxdepth 1 -mindepth 1 -type d | grep -oE "/[^/]+$" | cut -c 2-)"
all_envs="Create new env
$all_envs"

counter=0
for i in $(seq 1 $(printf "%s\n" "$all_envs" | wc -l)); do
    line="$(printf "%s\n" "$all_envs" | sed -n "$i"p)"
    echo "$counter. $line"
    counter=$((counter + 1))
done
counter=$((counter - 1))

input_as_number=""
while [[ -z "$input_as_number" ]]; do
    read -p "Enter your choice: " input
    if [[ "$input" =~ ^[0-9]+$ && "$input" -le "$counter" ]]; then
        input_as_number="$input"
    fi
done

if [[ "$input_as_number" -eq 0 ]]; then
    read -p "Name of new env: " envname
    read -p "Python version: " pyversion
    read -p "Packages to install (space-separated): " packages

    conda config --prepend channels defaults
    conda config --set channel_priority disabled
    conda create -y -n "$envname" python="$pyversion" pip ipython $packages

    env_dir="$folderPath/$envname"

    logfile="${env_dir}/ipythonlog.log"

    cat >"${env_dir}/pyexe" <<EOF
#!/bin/sh
touch _____tmp.py
conda deactivate
conda activate $envname
vtm -r term bash -c "ipython -i _____tmp.py -c=\"run \$1\" --Completer.use_jedi=True --Completer.greedy=True --Completer.suppress_competing_matchers=True --Completer.limit_to__all__=False --Completer.jedi_compute_type_timeout=10000 --Completer.evaluation='dangerous' --Completer.auto_close_dict_keys=True --PlainTextFormatter.max_width=9999 --HistoryManager.hist_file="~/ipython_hist.sqlite" --HistoryManager.db_cache_size=0 --TerminalInteractiveShell.xmode='Verbose' --TerminalInteractiveShell.space_for_menu=20 --TerminalInteractiveShell.history_load_length=10000 --TerminalInteractiveShell.history_length=100000 --TerminalInteractiveShell.display_page=True --TerminalInteractiveShell.autoformatter='black' --TerminalInteractiveShell.auto_match=True --logappend="~/anaconda3/envs/test/ipythonlog.log" --logfile="~/anaconda3/envs/test/ipythonlog.log" --InteractiveShell.history_load_length=10000 --InteractiveShell.history_length=100000 --cache-size=100000 --BaseIPythonApplication.log_level=30 --colors=Linux"

EOF
    chmod +x "${env_dir}/pyexe"
else
	input_as_number=$((input_as_number + 1))
	selected="$(printf "%s\n" "$all_envs" | sed -n "$input_as_number"p)"
    echo "You chose: $selected"
    cd "$folderPath/$selected"
    conda init
	conda activate "$selected"
	export DONT_PROMPT_WSL_INSTALL=1
    code "$folderPath/$selected"
fi

```

##

```
chmod +x ~/condalinux.sh
```

## VSCode config

```sh
{
    "code-runner.runInTerminal": true,
    "editor.autoClosingBrackets": "always",
    "editor.bracketPairColorization.independentColorPoolPerBracketType": true,
    "cmake.showOptionsMovedNotification": false,
    "workbench.startupEditor": "none",
    "terminal.explorerKind": "external",
    "python.terminal.activateEnvironment": false,
    "terminal.integrated.gpuAcceleration": "on",
    "terminal.integrated.scrollback": 1000000,
    "accessibility.verbosity.terminal": false,
    "accessibility.dimUnfocused.opacity": 1,
    "terminal.integrated.accessibleViewFocusOnCommandExecution": true,
    "terminal.integrated.accessibleViewPreserveCursorPosition": true,
    "terminal.external.windowsExec": "/bin/bash",
    "editor.accessibilityPageSize": 1,
    "editor.accessibilitySupport": "off",
    "editor.definitionLinkOpensInPeek": true,
    "editor.emptySelectionClipboard": false,
    "editor.experimentalWhitespaceRendering": "off",
    "editor.fastScrollSensitivity": 4,
    "editor.foldingMaximumRegions": 500,
    "editor.gotoLocation.alternativeTypeDefinitionCommand": "editor.action.goToImplementation",
    "editor.gotoLocation.multipleDeclarations": "gotoAndPeek",
    "editor.guides.bracketPairs": true,
    "editor.inlayHints.padding": true,
    "editor.mouseWheelScrollSensitivity": 1.1,
    "editor.multiCursorLimit": 50000,
    "editor.padding.bottom": 1,
    "editor.padding.top": 1,
    "editor.tabCompletion": "on",
    "editor.stickyTabStops": true,
    "editor.unfoldOnClickAfterEndOfLine": true,
    "editor.unicodeHighlight.nonBasicASCII": false,
    "editor.wrappingIndent": "indent",
    "editor.fontWeight": "normal",
    "editor.formatOnPaste": true,
    "diffEditor.experimental.showMoves": true,
    "diffEditor.hideUnchangedRegions.enabled": true,
    "diffEditor.hideUnchangedRegions.minimumLineCount": 1,
    "diffEditor.maxComputationTime": 0,
    "diffEditor.maxFileSize": 0,
    "multiDiffEditor.experimental.enabled": true,
    "editor.minimap.scale": 1,
    "editor.inlineSuggest.showToolbar": "always",
    "editor.quickSuggestions": {
        "other": "on",
        "comments": "on",
        "strings": "on"
    },
    "editor.quickSuggestionsDelay": 3,
    "editor.screenReaderAnnounceInlineSuggestion": false,
    "editor.suggest.filterGraceful": false,
    "editor.suggest.matchOnWordStartOnly": false,
    "editor.suggest.preview": true,
    "editor.suggest.shareSuggestSelections": true,
    "editor.suggestSelection": "first",
    "files.autoGuessEncoding": true,
    "files.defaultLanguage": "Python",
    "files.hotExit": "off",
    "files.participants.timeout": 0,
    "files.readonlyFromPermissions": true,
    "files.simpleDialog.enable": true,
    "workbench.commandPalette.experimental.suggestCommands": true,
    "workbench.commandPalette.history": 50000,
    "workbench.commandPalette.preserveInput": true,
    "workbench.enableExperiments": false,
    "workbench.experimental.share.enabled": true,
    "workbench.list.fastScrollSensitivity": 6,
    "workbench.list.scrollByPage": true,
    "workbench.list.smoothScrolling": true,
    "workbench.localHistory.maxFileEntries": 5000,
    "workbench.localHistory.maxFileSize": 8192,
    "workbench.reduceMotion": "on",
    "workbench.tips.enabled": false,
    "workbench.tree.enableStickyScroll": true,
    "workbench.editor.autoLockGroups": {
        "terminalEditor": false
    },
    "workbench.editor.limit.enabled": false,
    "workbench.settings.enableNaturalLanguageSearch": false,
    "workbench.editor.wrapTabs": true,
    "workbench.editor.limit.value": 10000,
    "workbench.editor.pinnedTabsOnSeparateRow": true,
    "workbench.editor.sharedViewState": true,
    "window.enableMenuBarMnemonics": false,
    "window.restoreFullscreen": true,
    "accessibility.dimUnfocused.enabled": true,
    "search.searchEditor.reusePriorSearchConfiguration": true,
    "search.seedWithNearestWord": true,
    "search.showLineNumbers": true,
    "search.smartCase": true,
    "search.useGlobalIgnoreFiles": true,
    "debug.allowBreakpointsEverywhere": true,
    "debug.autoExpandLazyVariables": "on",
    "debug.console.closeOnEnd": true,
    "debug.inlineValues": "on",
    "scm.alwaysShowRepositories": true,
    "scm.inputMaxLines": 50,
    "terminal.integrated.allowMnemonics": false,
    "terminal.integrated.autoReplies": {
        "Terminate batch job (Y/N)": "Y\r"
    },
    "terminal.integrated.confirmOnKill": "never",
    "terminal.integrated.copyOnSelection": false,
    "terminal.integrated.cursorBlinking": true,
    "terminal.integrated.cursorStyleInactive": "block",
    "terminal.integrated.defaultLocation": "editor",
    "terminal.integrated.defaultProfile.windows": "Command Prompt",
    "terminal.integrated.ignoreBracketedPasteMode": true,
    "terminal.integrated.windowsEnableConpty": true,
    "accessibility.hideAccessibleView": true,
    "security.workspace.trust.untrustedFiles": "open",
    "pieces.setCopilotLocation": true,
    "[python]": {
        "editor.defaultFormatter": "charliermarsh.ruff"
    },
    "workbench.iconTheme": "material-icon-theme",
    "C_Cpp.intelliSenseEngine": "disabled",
    "bookmarks.useWorkaroundForFormatters": true,
    "ruff.showNotifications": "always",
    "ruff.trace.server": "verbose",
    "ruff.ignoreStandardLibrary": false,
    "python.analysis.userFileIndexingLimit": -1,
    "python.analysis.autoImportCompletions": true,
    "bookmarks.keepBookmarksOnLineDelete": true,
    "bookmarks.sideBar.expanded": true,
    "python.analysis.enablePytestSupport": false,
    "python.analysis.gotoDefinitionInStringLiteral": true,
    "clangd.checkUpdates": true,
    "clangd.path": "/usr/bin/clangd",
    "python.analysis.completeFunctionParens": true,
    "bashIde.shellcheckPath": "/usr/bin/shellcheck",
    "codeium.enableConfig": {
        "*": true
    },
    "checkpoints.addCheckpointOnSave": true,
    "checkpoints.locale": "pt-BR",
    "rewrap.wrappingColumn": 72,
    "vscode-color-picker.languages": [
        "python",
        "javascript",
        "typescript",
        "C"
    ],
    "python.languageServer": "Jedi",
    "python.analysis.diagnosticSeverityOverrides": {
        "strictListInference": "none",
        "strictDictionaryInference": "none",
        "strictSetInference": "none",
        "analyzeUnannotatedFunctions": "none",
        "strictParameterNoneValue": "none",
        "enableTypeIgnoreComments": "none",
        "deprecateTypingAliases": "none",
        "enableExperimentalFeatures": "none",
        "disableBytesTypePromotions": "none",
        "reportGeneralTypeIssues": "none",
        "reportPropertyTypeMismatch": "none",
        "reportFunctionMemberAccess": "none",
        "reportMissingImports": "none",
        "reportMissingModuleSource": "none",
        "reportInvalidTypeForm": "none",
        "reportMissingTypeStubs": "none",
        "reportImportCycles": "none",
        "reportUnusedImport": "none",
        "reportUnusedClass": "none",
        "reportUnusedFunction": "none",
        "reportUnusedVariable": "none",
        "reportDuplicateImport": "none",
        "reportWildcardImportFromLibrary": "none",
        "reportAbstractUsage": "none",
        "reportArgumentType": "none",
        "reportAssertTypeFailure": "none",
        "reportAssignmentType": "none",
        "reportAttributeAccessIssue": "none",
        "reportCallIssue": "none",
        "reportInconsistentOverload": "none",
        "reportIndexIssue": "none",
        "reportInvalidTypeArguments": "none",
        "reportNoOverloadImplementation": "none",
        "reportOperatorIssue": "none",
        "reportOptionalSubscript": "none",
        "reportOptionalMemberAccess": "none",
        "reportOptionalCall": "none",
        "reportOptionalIterable": "none",
        "reportOptionalContextManager": "none",
        "reportOptionalOperand": "none",
        "reportRedeclaration": "none",
        "reportReturnType": "none",
        "reportTypedDictNotRequiredAccess": "none",
        "reportUntypedFunctionDecorator": "none",
        "reportUntypedClassDecorator": "none",
        "reportUntypedBaseClass": "none",
        "reportUntypedNamedTuple": "none",
        "reportPrivateUsage": "none",
        "reportTypeCommentUsage": "none",
        "reportPrivateImportUsage": "none",
        "reportConstantRedefinition": "none",
        "reportDeprecated": "none",
        "reportIncompatibleMethodOverride": "none",
        "reportIncompatibleVariableOverride": "none",
        "reportInconsistentConstructor": "none",
        "reportOverlappingOverload": "none",
        "reportPossiblyUnboundVariable": "none",
        "reportMissingSuperCall": "none",
        "reportUninitializedInstanceVariable": "none",
        "reportInvalidStringEscapeSequence": "none",
        "reportUnknownParameterType": "none",
        "reportUnknownArgumentType": "none",
        "reportUnknownLambdaType": "none",
        "reportUnknownVariableType": "none",
        "reportUnknownMemberType": "none",
        "reportMissingParameterType": "none",
        "reportMissingTypeArgument": "none",
        "reportInvalidTypeVarUse": "none",
        "reportCallInDefaultInitializer": "none",
        "reportUnnecessaryIsInstance": "none",
        "reportUnnecessaryCast": "none",
        "reportUnnecessaryComparison": "none",
        "reportUnnecessaryContains": "none",
        "reportAssertAlwaysTrue": "none",
        "reportSelfClsParameterName": "none",
        "reportImplicitStringConcatenation": "none",
        "reportUndefinedVariable": "none",
        "reportUnboundVariable": "none",
        "reportInvalidStubStatement": "none",
        "reportIncompleteStub": "none",
        "reportUnsupportedDunderAll": "none",
        "reportUnusedCallResult": "none",
        "reportUnusedCoroutine": "none",
        "reportUnusedExcept": "none",
        "reportUnusedExpression": "none",
        "reportUnnecessaryTypeIgnoreComment": "none",
        "reportMatchNotExhaustive": "none",
        "reportImplicitOverride": "none",
        "reportShadowedImports": "none",
    },
    "python.analysis.inlayHints.variableTypes": false,
    "python.analysis.inlayHints.pytestParameters": false,
    "python.analysis.inlayHints.functionReturnTypes": false,
    "python.analysis.persistAllIndices": false,
    "python.analysis.logLevel": "Error",
    "explorerExclude.showPicker": false,
    "workbench.activityBar.location": "top",
    "ruff.lint.args": [
        "--select=ALL",
        "--extend-select=UP",
        "--fix",
        "--unsafe-fixes"
    ],
    "material-icon-theme.files.color": "#26a69a",
    "explorer.confirmDelete": false,
    "workbench.editorAssociations": {
        "*.jpg": "luna.editor"
    },

    "editor.defaultFormatter": "charliermarsh.ruff",
    "editor.mouseWheelZoom": true,
    "window.zoomLevel": -1,
    "debug.internalConsoleOptions": "neverOpen",
    "clipboard-manager.snippet.enabled": false,
    "codeium.aggressiveShutdown": true,
    "shellcheck.exclude": [
        "SC3054",
        "SC3030"
    ],
    "files.eol": "\n",
    "workbench.editor.highlightModifiedTabs": true,
    "luna.retainContextWhenHidden": false,
    "prettier.resolveGlobalModules": true,
    "git.openRepositoryInParentFolders": "never",
    "search.quickAccess.preserveInput": true,
    "window.menuBarVisibility": "compact",
    "files.autoSave": "afterDelay"
}
```
