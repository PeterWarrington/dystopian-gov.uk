---
layout: basic
title:  Register to protest form
---

<div class="govuk-breadcrumbs">
    <ol class="govuk-breadcrumbs__list">
    <li class="govuk-breadcrumbs__list-item">
        <a class="govuk-breadcrumbs__link" href="/">Home</a>
    </li>
    <li class="govuk-breadcrumbs__list-item">
        <a class="govuk-breadcrumbs__link" href="/register-to-protest">
            Register to protest
        </a>
    </li>
    <li class="govuk-breadcrumbs__list-item" aria-current="page">Register</li>
    </ol>
</div>

<main class="govuk-main-wrapper " id="main-content" role="main">
    <div class="govuk-grid-row">
    <div class="govuk-grid-column-two-thirds">
        <h1 class="govuk-heading-xl">
            Register to protest
            <span class="govuk-caption-xl">Use this form to register to protest legally.</span>
        </h1>

        <div class="govuk-warning-text">
            <span class="govuk-warning-text__icon" aria-hidden="true">!</span>
            <strong class="govuk-warning-text__text">
                <span class="govuk-warning-text__assistive">Warning</span>
                Providing false information on this form can lead to imprisonment without charge.
            </strong>
        </div>
        
        <fieldset class="govuk-fieldset">
            <div class="govuk-form-group">
                <label class="govuk-label" for="name">
                    Full Name
                </label>
                <span id="name-empty-error" class="govuk-error-message" style="display:none;">
                    <span class="govuk-visually-hidden">Error:</span> Please enter a name.
                </span>
                <input class="govuk-input govuk-!-width-two-thirds" id="name" name="name" type="text">
            </div>

            <div class="govuk-form-group">
                <label class="govuk-label" for="name">
                    Government Identity Number
                </label>
                <span id="GIN-empty-error" class="govuk-error-message" style="display:none;">
                    <span class="govuk-visually-hidden">Error:</span> Please enter your Government Identity Number.
                </span>
                <input class="govuk-input govuk-!-width-two-thirds" id="GIN" name="address-town" type="text">
            </div>
            
            <div class="govuk-form-group">
                <label class="govuk-label" for="address-line-1">
                Home address
                <span id="address-empty-error" class="govuk-error-message" style="display:none;">
                    <span class="govuk-visually-hidden">Error:</span> Please enter a address.
                </span>
                <span class="govuk-visually-hidden">line 1 of 2</span>
                </label>
                <input class="govuk-input" id="address-line-1" name="address-line-1" type="text">
            </div>
            
            <div class="govuk-form-group">
                <label class="govuk-label" for="address-line-2">
                <span class="govuk-visually-hidden">Home address line 2 of 2</span>
                </label>
                <span id="address-empty-error" class="govuk-error-message" style="display:none;">
                    <span class="govuk-visually-hidden">Error:</span> Please enter a address.
                </span>
                <input class="govuk-input" id="address-line-2" name="address-line-2" type="text">
            </div>
            
            <div class="govuk-form-group">
                <label class="govuk-label" for="address-town">
                Home Town or city
                </label>
                <span id="city-empty-error" class="govuk-error-message" style="display:none;">
                <span class="govuk-visually-hidden">Error:</span> Please enter your Home town or city.
                </span>
                <input class="govuk-input govuk-!-width-two-thirds" id="address-town" name="address-town" type="text">
            </div>
            
            <div class="govuk-form-group">
                <label class="govuk-label" for="address-county">
                Home County
                </label>
                <span id="county-empty-error" class="govuk-error-message" style="display:none;">
                <span class="govuk-visually-hidden">Error:</span> Please enter your county.
                </span>
                <input class="govuk-input govuk-!-width-two-thirds" id="address-county" name="address-county" type="text">
            </div>
            
            <div class="govuk-form-group">
                <label class="govuk-label" for="address-postcode">
                Postcode
                </label>
                <span id="postcode-empty-error" class="govuk-error-message" style="display:none;">
                <span class="govuk-visually-hidden">Error:</span> Please enter a postcode.
                </span>
                <input class="govuk-input govuk-input--width-10" id="address-postcode" name="address-postcode" type="text">
            </div>

            <span class="govuk-hint">
                Entering details of the protest is not necessary.
            </span>

            <button type="submit" class="govuk-button" id="submit">
                Save and continue
            </button>

            <span id="global-error" class="govuk-error-message" style="display:none;">
                <span class="govuk-visually-hidden">Error:</span> Please see above errors.
            </span>
            
            </fieldset>
    </div>
    </div>
</main>

<script>
    document.getElementById("submit").addEventListener("click", () => {
        formGroups = document.getElementsByClassName("govuk-form-group");
        submit = true;
        // for (i=0; i < formGroups.length; i++) {
        //   if (formGroups[i].getElementsByClassName("govuk-input")[0].value.trim() == "") {
        //     submit = false;
        //     formGroups[i].getElementsByClassName("govuk-error-message")[0].style = "display: block";
        //   } else {
        //     formGroups[i].getElementsByClassName("govuk-error-message")[0].style = "display: none";
        //   }
        // }
        if (submit) {
        document.getElementById("global-error").style = "display: none";
        window.location.replace("/register-to-protest/register/thank-you");
        } else {
        document.getElementById("global-error").style= "display:block";
        }
    });
</script>