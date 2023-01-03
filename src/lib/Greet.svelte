<script>
  let pw = "";
  let greetMsg = "";
  let appAccess = false;

  const checkPw = () => {
    if (!pw) return;

    if (pw.toLowerCase() === "teşekkürler erkut") {
      appAccess = true;
      greetMsg = "Giriş başarılı.";
    } else {
      appAccess = false;
      greetMsg = "Tekrar deneyin.";
      pw = "";
    }
  };
</script>

<div class="flex flex-col gap-2">
  <form on:submit|preventDefault={checkPw} class="row">
    <input id="greet-input" placeholder="Mesajınız..." bind:value={pw} />
    <button on:click={checkPw}> Gönder </button>
  </form>
  <p class={appAccess ? "text-green-400" : "text-red-500"}>{greetMsg}</p>
</div>
