---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewApplication()
tags := []string {
	"HR",
	"Payroll",
	"HideApp",

}
requestBody.SetTags(tags)
info := graphmodels.NewInformationalUrl()
logoUrl := "https://cdn.pixabay.com/photo/2016/03/21/23/25/link-1271843_1280.png"
info.SetLogoUrl(&logoUrl) 
marketingUrl := "https://www.contoso.com/app/marketing"
info.SetMarketingUrl(&marketingUrl) 
privacyStatementUrl := "https://www.contoso.com/app/privacy"
info.SetPrivacyStatementUrl(&privacyStatementUrl) 
supportUrl := "https://www.contoso.com/app/support"
info.SetSupportUrl(&supportUrl) 
termsOfServiceUrl := "https://www.contoso.com/app/termsofservice"
info.SetTermsOfServiceUrl(&termsOfServiceUrl) 
requestBody.SetInfo(info)
web := graphmodels.NewWebApplication()
homePageUrl := "https://www.contoso.com/"
web.SetHomePageUrl(&homePageUrl) 
logoutUrl := "https://www.contoso.com/frontchannel_logout"
web.SetLogoutUrl(&logoutUrl) 
redirectUris := []string {
	"https://localhost",

}
web.SetRedirectUris(redirectUris)
requestBody.SetWeb(web)

result, err := graphClient.ApplicationsById("application-id").Patch(context.Background(), requestBody, nil)


```