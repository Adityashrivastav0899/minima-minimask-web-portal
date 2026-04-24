function hasMiniMask() {
  return typeof window.MINIMASK !== "undefined";
}

function connect() {
  if (!hasMiniMask()) {
    alert("Install MiniMask extension (desktop only)");
    return;
  }

  window.MINIMASK.init(() => {

    window.MINIMASK.account.getAddress((res) => {
      document.getElementById("address").innerText =
        res.address || res;
    });

    window.MINIMASK.account.getPublicKey((res) => {
      document.getElementById("pubkey").innerText =
        res.publickey || res;
    });

  });
}

function getBalance() {
  window.MINIMASK.account.balance((res) => {
    document.getElementById("balance").innerText =
      JSON.stringify(res, null, 2);
  });
}

function send() {
  const to = document.getElementById("to").value;
  const amount = document.getElementById("amount").value;

  window.MINIMASK.account.send(to, amount, "0x00", (res) => {
    document.getElementById("output").innerText =
      JSON.stringify(res, null, 2);
  });
}
