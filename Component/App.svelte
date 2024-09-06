<script>
  import { App } from "./../dist/index.mjs";

  import {
    LocalStorageTransporter,
    PeerjsTransporter
  } from "./../transporter/index.js";

  function createTransporter({ role, uid }) {
    return new LocalStorageTransporter();
  }
</script>
<App lang="en-US" {createTransporter} />