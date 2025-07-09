# GitHub Action Test Page

This page is created to test the automated link checking GitHub Action workflow.

## Internal Links (should work)
- [Home](index.md) - Link to main documentation page
- [Useful Resources](useful-resources.md) - Link to resources page

## External Links (should work)
- [GitHub](https://github.com) - Should be accessible
- [Python.org](https://python.org) - Should be accessible  
- [Sphinx Documentation](https://www.sphinx-doc.org/) - Should be accessible

## Test Scenarios

### Valid Links
All the links above should pass the link checker validation.

### Link Checker Features Tested
1. **Internal navigation** - Links between documentation pages
2. **External references** - Links to external websites
3. **Anchor links** - Links to sections within pages
4. **Protocol handling** - HTTP/HTTPS links

## Expected Results
When this PR is created, the GitHub Action should:

1. ✅ Wait for ReadTheDocs preview to deploy
2. ✅ Run muffet link checker on the preview
3. ✅ Find all links are valid (after fixes applied)
4. ✅ Post a success comment on the PR
5. ✅ Pass the status check

## Documentation
This page demonstrates the automated quality assurance process for wafer.space documentation.