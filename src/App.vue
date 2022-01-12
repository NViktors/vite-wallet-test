<template>
  <div class="wrapper">
    <wallet-provider :auto-connect="true" :wallets="wallets">
      <wallet-modal-provider>
        <wallet-multi-button/>
      </wallet-modal-provider>
    </wallet-provider>
  </div>
</template>

<style lang="scss">
.wrapper {
  margin: 0 auto;
  display: flex;
  width: 80%;
  align-content: center;
  justify-content: center;
  // flex-direction: column;
}
</style>

<script setup lang="ts">
  import {WalletProvider} from "@solana/wallet-adapter-vue";
  import {getPhantomWallet, getSolflareWallet} from '@solana/wallet-adapter-wallets';
  import {WalletModalProvider, WalletMultiButton} from "@solana/wallet-adapter-vue-ui";

  const wallets = [
    getPhantomWallet(),
    getSolflareWallet()
  ];
</script>

