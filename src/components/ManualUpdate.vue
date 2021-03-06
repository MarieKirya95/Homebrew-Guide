<template>
    <div class="ui container">
        <div class="ui segment" v-bind:class="{ inverted: $root.$data.darkTheme }">
            <h1 class="ui header" style="text-align:center">
                Updating/Downgrading Manually Without Burning Fuses
            </h1>
            <div class="ui divider"></div>
            <p>When you update your system firmware version, your Nintendo Switch burns a microscopic fuse to prevent your Switch from being able to downgrade. Essentially, if a firmware tries to boot but too many fuses are burnt for that specific firmware version, the system will simply power off, preventing you from booting.<br/><br/>
            Hekate, ReiNX and SXOS bypass these fuse checks and the fuse burns. By enabling AutoRCM and then manually updating using ChoiDujourNX, you can keep your Switch in a state where it can be downgraded again the future.<br/><br/>
            You can also use this guide as a way to upgrade your Switch if your Switch does not have access to the internet or is superbanned, and to downgrade your Switch to any firmware version.</p>
        </div>

        <div class="ui teal message" style="text-align:center" v-bind:class="{ inverted: $root.$data.darkTheme }">
            If something goes wrong or you need help, check <router-link to="/troubleshooting">troubleshooting</router-link>.
        </div>


        <div class="ui red message" v-bind:class="{ inverted: $root.$data.darkTheme }">
            <h2 class="ui header" style="text-align:center">
                IMPORTANT: Understanding AutoRCM
            </h2>
            <div class="ui divider"></div>
            <p><b style="color:red">A later step will give you the option to enable or disable AutoRCM. </b>AutoRCM is a software method of forcing your Switch to go into RCM on every launch, without the need of a jig or hardmod. Essentially, you are purposefully bricking your Switch in a controlled matter that forces it to launch into recovery. This might sound scary but is not actually dangerous, and can be undone at any time.<br><br>
            AutoRCM has the following benefits:
            </p>
            <ul>
                <li>The Switch will not burn any fuses, meaning you can downgrade your Switch to a lower firmware version in the future should the need arise.</li>
                <li>You will never accidentally boot stock firmware, meaning you can avoid having telemetry data accidentally sent to Nintendo.</li>
            </ul>
            <p style="color:red">AutoRCM has the following disadvantages:</p>
            <ul>
                <li>You will not be able to boot your Switch at all without a payload sender.</li>
                <li>Your Switch will not turn off correctly from the Switch OS. You will have to shutdown from a payload like Hekate.</li>
            </ul>
            <p>
                It is <b>highly recommended that you enable AutoRCM</b> as if you ever boot your Switch without Hekate, your fuses will burn and you will not be able to cleanly downgrade again in the future.
            </p>
            <div class="ui info message" style="text-align:center" v-bind:class="{ inverted: $root.$data.darkTheme }">
                If you just want to manually update your system firmware and do not care about burning fuses, you can leave AutoRCM disabled.
            </div>
            <div class="ui red message" style="text-align:center" v-bind:class="{ inverted: $root.$data.darkTheme }">
                If you are downgrading to a firmware expecting less fuses burnt than you have, <b style="color:red">AutoRCM is required to boot your Switch</b> until you upgrade again.
            </div>

            <p>AutoRCM can always be disabled <b>Hekate > Tools > AutoRCM</b></p>
        </div>

        <div class="ui segment" v-bind:class="{ inverted: $root.$data.darkTheme }">
            <h2 class="ui header" style="text-align:center">
                Step 1: Preparing Files
            </h2>
            <div class="ui divider"></div>
            <ol>
                <li>You need to locate the firmware binaries for the firmware version you want to downgrade to. These cannot be shared here as they are copyrighted (hint: darthsternie, xbins)</li>
                <li>Make sure your SD card includes a basic Hekate/Atmosphere setup (such as the one installed when following this guide)</li>
                <li>Insert your SD card into your PC</li>
                <li>Create a new folder on the root of your SD card named <b>"firmware"</b></li>
                <li>Extract <b>the contents</b> of your firmware archive file into the new <b>/firmware</b> folder on your SD card</li>
                <li>Go to <a href="https://switchtools.sshnuke.net/">switchtools.sshnuke.net</a></li>
                <li>Download the latest version of ChoiDujourNX by rajkosto</li>
                <li>Extract the <b>ChoiDujourNX.nro</b> file within the downloaded .ZIP file into the <b>/switch</b> folder on your SD card</li>
            </ol>
        </div>

        <div class="ui segment" v-bind:class="{ inverted: $root.$data.darkTheme }">
            <h2 class="ui header" style="text-align:center">
                Step 2: Installing the New Firmware Version
            </h2>
            <div class="ui divider"></div>
            <ol>
                <li>Insert your SD card into your Switch</li>
                <li>Run Hekate using your payload sender of choice</li>
                <li>Launch CFW <b>(Launch > CFW)</b></li>
                <li><b>IMPORTANT: Plug your Switch in to prevent the Switch from dying midway through the install process</b></li>
                <li>Enter the Homebrew Menu through Album</li>
                <li>Select <b>ChoiDujourNX</b></li>
                <li>In ChoiDujourNX, enter the <b>/firmware</b> you created earlier and select <b>Choose</b> </li>
                <li>After processing, select <b>[x.x.x] (exFAT)</b> where [x.x.x] is the firmware version you chose</li>
                <li>After verification, choose <b>Select Firmware</b></li>
                <li>Choose whether you want to enable or disable AutoRCM (see above for more information). <b>This will override an existing AutoRCM settings you have, so make sure to pick which you want.</b></li>
                <li>Choose <b>Start installation</b></li>
                <li>Wait for the firmware update to finish
                    <ul><li>This can be take little time or a long time depending on the situation. Be patient, and don't worry if it finishes very quickly.</li></ul></li>
                <li>After installation, select <b>Reboot</b> and then <b>Shutdown Now!</b></li>
            </ol>

            <p>You can now delete the <b>/firmware</b> folder on your SD card.</p>
        </div>

        <div class="ui green message" style="text-align:center" v-bind:class="{ inverted: $root.$data.darkTheme }">
            Your Switch is now running the firmware version you chose!
        </div>

        <div class="ui divider"></div>

        <div class="ui purple message" v-bind:class="{ inverted: $root.$data.darkTheme }">
            <b>Back to <router-link to="/final">After Setup</router-link></b>
        </div>    </div>
</template>

<script>
    export default {
        name: "ManualExfat"
    }
</script>

<style scoped>

</style>