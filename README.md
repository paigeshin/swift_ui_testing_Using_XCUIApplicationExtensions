# swift_ui_testing_Using_XCUIApplicationExtensions

Most of my UI testing logic is now categories on XCUIApplication. Makes the test cases really easy to read:

```swift
func testLoggingInAndOut() {
    XCTAssertFalse(app.userIsLoggedIn)
    
    app.launch()
    app.login()
    XCTAssertTrue(app.userIsLoggedIn)
    
    app.logout()
    XCTAssertFalse(app.userIsLoggedIn)
}

func testDisplayingCategories() {
    XCTAssertFalse(app.isDisplayingCategories)
    
    app.launch()
    app.login()
    app.goToCategories()
    XCTAssertTrue(app.isDisplayingCategories)
}
```
