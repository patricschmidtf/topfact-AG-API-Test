# QuickIndexReset

## QuickIndex Reset

**Functionality:** The `btnResetQuickIndex_Click` method is triggered when the user clicks the 'Reset QuickIndex' button to reset the QuickIndex settings.

**Why reset?** The window parameters for QuickIndex are outside a usable range and need to be reset. The document is not displayed!

**Description:**

* **Registry Paths:** Two paths to the registry keys are defined:
  * `keyName`: Path to `Software\pro effectus\topfact6 MyWork\DockManager`.
  * `keyName2`: Path to `Software\topfact\topfact6 MyWork\DockManager`.
* **Opening and Deleting Keys:** The method attempts to open the registry keys in the current user's area. If the key exists, the subkey `frmQuickIndex` and its contents are deleted.
* **Popup Message:** After resetting, a message appears: "The QuickIndex settings have been reset."
* **Error Handling:** If an error occurs, it is suppressed in the `catch` block, without showing a specific error message.

**Link to the part of the code for this function:** [<mark style="color:blue;">Link</mark>](https://github.com/topfact-AG/topfact6/blob/97253914e8f78c153a791c816fd44a15f42987ed/topfact.MyWork/topfact.MyWork/Forms/Settings/frmUserSettings.cs#L378)
