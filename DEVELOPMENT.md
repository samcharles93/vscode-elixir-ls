# Development

## Packaging

1. Make and push the elixir-ls tag
2. Update the elixir-ls submodule `git submodule foreach git pull origin master`

3. Test the new vscode-elixir-ls version with:

    ```
    npm install
    npm install -g vsce@latest
    cp elixir-ls/.release-tool-versions .tool-versions
    vsce package
    code --install-extension ./elixir-ls-0.2.44.vsix  --force
    ```

4. Ensure you have a clean git repository
5. `vsce publish 0.3.1` (or whatever version) (note that this will create a commit and a tag)
6. `git push upstream --tags`
7. Update forum announcement post: https://elixirforum.com/t/introducing-elixirls-the-elixir-language-server/5857

8. Also publish to https://open-vsx.org/

    - `git checkout openvsx`
    - `git rebase -i upstream/master`
    - `ovsx publish -p <TOKEN>`
    - `git push -f`

## References

https://code.visualstudio.com/api/working-with-extensions/publishing-extension

Personal Access Token (PAT) direct link: https://dev.azure.com/elixir-lsp/_usersSettings/tokens

https://code.visualstudio.com/api/language-extensions/embedded-languages

## VSCode grammar debugging

Run "Developer: Inspect Editor Tokens and Scopes" when you want to debug the textmate grammar
