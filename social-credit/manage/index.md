---
layout: basic
title:  Manage your Social Credit Score
---

<div class="govuk-breadcrumbs">
    <ol class="govuk-breadcrumbs__list">
    <li class="govuk-breadcrumbs__list-item">
        <a class="govuk-breadcrumbs__link" href="/">Home</a>
    </li>
    <li class="govuk-breadcrumbs__list-item">
        <a class="govuk-breadcrumbs__link" href="/social-credit">Manage your Social Credit Score</a>
    </li>
    <li class="govuk-breadcrumbs__list-item" aria-current="page">Manage</li>
    </ol>
</div>

<main class="govuk-main-wrapper " id="main-content" role="main">
    <div id="loading-indicator" style="opacity: 0;">
    <div class="lds-spinner"><div></div><div></div><div></div><div></div>
    <div></div><div></div><div></div><div></div><div></div><div></div><div>
    </div><div></div></div> <!-- This looks horrible. I stole it off the internet.
                                    But it works. So I don't care.-->
    <br/>
    <span style="color: #0b0c0c">Loading...</span>
    </div>

    <div class="govuk-grid-row" id="post-load-message" style="display: none">
    <div class="govuk-grid-column-two-thirds">
        <h1 class="govuk-heading-xl">
            British Identity Verification Error
        </h1>

        <p class="govuk-body">
            We were unable to obtain your British Identity details.
            Please ensure that you are accessing this service through a
            BritishMedia approved ISP, and that you are not using software 
            such as VPNs to circumvent the UK National Firewall, contrary 
            to the Criminal Communication Powers and Enforcement Act.
        </p>
        
        <div class="govuk-warning-text">
            <span class="govuk-warning-text__icon" aria-hidden="true">!</span>
            <strong class="govuk-warning-text__text">
                <span class="govuk-warning-text__assistive">Warning</span>
                Using software to circumvent the UK National Firewall
                can result in imprisonment without charge.
            </strong>
        </div>

    </div>
    </div>
</main>

<script>
function sleep(ms) { // https://stackoverflow.com/a/39914235
    return new Promise(resolve => setTimeout(resolve, ms));
}
async function fade(fadeType, id, length) {
    for (i=0; i < length; i++) {
    if (fadeType == "in") {
        opacityAdjustForFadeType = (i / length);
    } else {
        opacityAdjustForFadeType = (1 - (i / length));
    }
    await sleep(1);
    document.getElementById(id).style = "opacity: " + opacityAdjustForFadeType;
    }
    if (fadeType == "in") {
    document.getElementById(id).style = "opacity: 1";
    }
}

async function main() {
    await fade("in", "loading-indicator", 150);
    await sleep(3000);
    await fade("out", "loading-indicator", 150);
    document.getElementById("loading-indicator").style = "display: none";
    await fade("in", "post-load-message", 150);
}

main();
</script>

<style>
    #main-content {
        height: 300px;
        width: 960px; /* Same as width container */
        display: table-cell;
        vertical-align: middle;
    }
    #loading-indicator {
        display: block;
        width: 80px;
        margin: auto;
    }
    .lds-spinner {
        width: 64px;
        height: 64px;
    }
    .lds-spinner div {
        transform-origin: 32px 32px;
        animation: lds-spinner 1.2s linear infinite;
    }
    .lds-spinner div:after {
        content: " ";
        display: block;
        position: absolute;
        top: 3px;
        left: 29px;
        width: 5px;
        height: 14px;
        border-radius: 20%;
        background:#6f777b;
    }
    .lds-spinner div:nth-child(1) {
        transform: rotate(0deg);
        animation-delay: -1.1s;
    }
    .lds-spinner div:nth-child(2) {
        transform: rotate(30deg);
        animation-delay: -1s;
    }
    .lds-spinner div:nth-child(3) {
        transform: rotate(60deg);
        animation-delay: -0.9s;
    }
    .lds-spinner div:nth-child(4) {
        transform: rotate(90deg);
        animation-delay: -0.8s;
    }
    .lds-spinner div:nth-child(5) {
        transform: rotate(120deg);
        animation-delay: -0.7s;
    }
    .lds-spinner div:nth-child(6) {
        transform: rotate(150deg);
        animation-delay: -0.6s;
    }
    .lds-spinner div:nth-child(7) {
        transform: rotate(180deg);
        animation-delay: -0.5s;
    }
    .lds-spinner div:nth-child(8) {
        transform: rotate(210deg);
        animation-delay: -0.4s;
    }
    .lds-spinner div:nth-child(9) {
        transform: rotate(240deg);
        animation-delay: -0.3s;
    }
    .lds-spinner div:nth-child(10) {
        transform: rotate(270deg);
        animation-delay: -0.2s;
    }
    .lds-spinner div:nth-child(11) {
        transform: rotate(300deg);
        animation-delay: -0.1s;
    }
    .lds-spinner div:nth-child(12) {
        transform: rotate(330deg);
        animation-delay: 0s;
    }
    @keyframes lds-spinner {
        0% {
        opacity: 1;
        }
        100% {
        opacity: 0;
        }
    }
</style>