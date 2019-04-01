# Releasing a Patch for LSB2

#### Procedures

Once you can compile LSB2 in Visual Studio with the **Debug** Configuration and have tested your change locally,

 1. Edit the Application Properties (**LSB.Application B Properties...** under the **Project** menu), click **Assembly Information...** and increment the Assembly Version
 2. Change the Configuration to **Release**
 3. Build the Solution
 4. Run the application **Git Bash** and type
    >     cd M:/Emerging\ Products/BUILDER
    >     rake lsb:builds:prepare
    >     rake lsb:msi:create
    >     rake lsb:msp:create from=203011 to=203012
    >     rake lsb:publish from=203011 to=203012
    > (replace the `from` and `to` parameters with the correct version numbers)
    >
    > - The first `rake` task copies the executables to a folder named for the new Assembly Version
    > - The second `rake` task compiles an installer for the executables
    > - The third `rake` task creates a patch from one version of LSB2 to another (you might create more than one patch to create an upgrade path from multiple start versions to the new target version)
    > - The fourth `rake` task launches `updup.exe` with most details filled in. There's a text box to add Notes. The **Update path** is set to Internal by default which will make the patch available to anyone whose customer number is 70000001.
 5. After verifying the patch internally, run `updup.exe`, find the patch under **Active patches**, and change its **Update path** to Release.
