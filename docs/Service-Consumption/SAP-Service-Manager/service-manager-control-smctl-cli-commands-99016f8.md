<!-- loio99016f83ce8e4d049316b61b5cadf1fc -->

# Service Manager Control \(SMCTL\) CLI Commands

A list of all tasks and respective commands that are available in the SMCTL for SAP BTP.

All commands are executed in the global account. If you want to work in a specific subaccount or directory, we recommend to set the default context once by using `sapcp target`. This way, you do not have to pass the subaccount or directory parameter with every command.

You can find extensive help about each command directly in the SMCTL by using the `--help` option. For example, use `sapcp --help list accounts/subaccount` for help on how to use `sapcp list accounts/subaccount`.

The following commands are available:

-   login and logout

    -   [login](login-a8ed7cf.md)

    -   [logout](logout-54f7e42.md)


-   bindings

    -   [get-binding](get-binding-8495036.md)

    -   [list-bindings](list-bindings-0078d1a.md)

    -   [bind](bind-f53ff26.md)

    -   [unbind](unbind-19fadcd.md)


-   brokers

    -   [register-broker](register-broker-3e7a312.md)

    -   [update-broker](update-broker-c5acdba.md)

    -   [list-brokers](list-brokers-75386b8.md)

    -   [delete-broker](delete-broker-f3018c2.md)


-   platforms

    -   [register-platform](register-platform-4fe2d10.md)

    -   [update-platform](update-platform-f930dbc.md)

    -   [list-platforms](list-platforms-98f4461.md)

    -   [delete-platform](delete-platform-be41510.md)


-   instances

    -   [provision](provision-b327b66.md)

    -   [get-instance](get-instance-24fb85c.md)

    -   [list-instances](list-instances-728f1b6.md)

    -   [deprovision](deprovision-f48502c.md)


-   offerings

    -   [list-offerings](list-offerings-8a0659f.md)

    -   [list-plans](list-plans-b0e4863.md)

    -   [marketplace](marketplace-ae6874a.md)


-   other commands

    -   [status](status-37936ee.md)

    -   [info](info-4d2bb71.md)

    -   [version](version-bcb35b8.md)

    -   [help](help-556cb8a.md)



-   **[Login and Logout](login-and-logout-fcc37a9.md "")**  

-   **[Platforms](platforms-a6d96ec.md "")**  

-   **[Brokers](brokers-743f3f7.md "")**  

-   **[Instances](instances-23af00d.md "")**  

-   **[Bindings](bindings-c9763ce.md "")**  

-   **[Offerings](offerings-5708056.md "")**  

-   **[Other Commands](other-commands-8af0691.md "")**  


**Related Information**  


[Set the Default Command Context](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/720645a3ed3945bd8d97a670b948ac07.html)

[Using the Service Manager Control \(SMCTL\) Command-Line Tool](using-the-service-manager-control-smctl-command-line-tool-0107f3f.md "Use the Service Manager Control (SMCTL) command-line tool to manage environments, brokers, service instances, and service bindings in SAP Service Manager environment.")

