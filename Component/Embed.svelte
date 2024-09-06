<script>
  import { Embed } from "./../dist/index.mjs";

  import {
    LocalStorageTransporter,
    PeerjsTransporter
  } from "./../transporter/index.js";

  function createTransporter({ role, uid }) {
    return new LocalStorageTransporter();
  }
</script>
<Embed lang="en-US" {createTransporter} />