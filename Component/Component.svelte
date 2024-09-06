<script>
  import { App, Embed, setCurrentLanguage } from "./../dist/index.mjs";
  import "./../dist/style.css";
  import {
    LocalStorageTransporter,
    PeerjsTransporter
  } from "@syncit/transporter";
  import { onMount } from "svelte";

  function createTransporter({ role, uid }) {
    return new LocalStorageTransporter();
  }

  function init(el) {
    new syncit.App({
      target: el,
      props: {
        createTransporter({ role, uid }) {
          return new PeerjsTransporter({
            role,
            uid,
            peerHost: "localhost",
            peerPort: 9000,
            peerPath: "/myapp"
          });
        }
      }
    });
  }
</script>



<App lang="en-US" {createTransporter} />
<Embed lang="en-US" {createTransporter} />


