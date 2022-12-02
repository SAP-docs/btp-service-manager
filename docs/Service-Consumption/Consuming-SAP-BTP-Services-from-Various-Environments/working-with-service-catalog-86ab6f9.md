<!-- loio86ab6f98820a4c468b717c08ac74824e -->

# Working with Service Catalog



## Procedure

1.  In order to use the Service Catalog and see the marketplace, install the Service Catalog CLI by executing the following commands:

    -   For Mac OS:

        ```
        curl -sLO https://download.svcat.sh/cli/latest/darwin/amd64/svcat
        ```

        ```
        chmod +x ./svcat
        ```

        ```
        mv ./svcat /usr/local/bin/
        ```

        ```
        svcat version --client
        ```

    -   For Windows OS:

        ```
        iwr 'https://download.svcat.sh/cli/latest/windows/amd64/svcat.exe' -UseBasicParsing -OutFile svcat.exe
        ```

        ```
        mkdir -f ~\bin
        ```

        ```
        Move-Item -Path svcat.exe  -Destination ~\binMove-Item -Path svcat.exe  -Destination ~\bin
        ```

        ```
        $env:PATH += ";${pwd}\bin"
        ```

        ```
        svcat version --client
        ```


    See [Install the Service Catalog CLI](https://svc-cat.io/docs/install/#installing-the-service-catalog-cli).

2.  Use the Service Catalog CLI to present the list of all the SAP BTP services available for the Kubernetes environment:

    ```
    svcat marketplace
    ```

    or

    ```
    svcat mp
    ```

3.  Create an instance of any service, by specifying its name and plan:

    ```
    svcat provision <Enter a name for the instance> --class xsuaa --plan application
    ```

4.  Verify the service instance was created successfully:

    ```
    svcat get instances
    ```

5.  Delete the service instance:

    ```
    svcat deprovision INSTANCE-NAME
    ```


