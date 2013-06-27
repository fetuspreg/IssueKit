# IssueKit
A drop-in component for creating GitHub issues in your app.
**You should only have this in debug builds.**

# How to use

Get an API access token from [GitHub](https://github.com/settings/applications).

Setup `ISKIssueManager` in `application:didFinishLaunchingWithOptions:`

```Objective-C
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    // Reponame must be in 'username/reponame' format.

    [[ISKIssueManager defaultManager] setupWithReponame:@"usepropeller/IssueKit" andAccessToken:@"access token"];
    return YES;
}
```

Call `-presentIssueViewControllerOnViewController` when you want to show the issue prompt.

```Objective-C
- (IBAction)showIssueViewController:(id)sender {
    [[ISKIssueManager defaultManager] presentIssueViewControllerOnViewController:self];
}
```

That's it! IssueKit will create an issue with an 'IssueKit' label on the repo you specified.