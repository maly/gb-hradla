## 16.2 Negované signály {#16-2-negovan-sign-ly}

Možná jste si říkali, proč jsou některé signály v číslicové technice negované. Typicky třeba signál RESET a signály řízení sběrnice bývají navržené tak, že jsou aktivní v log. 0, a v klidovém stavu jsou v log. 1\. Důvodem je rušení. Představte si, že se ve vedení indukuje rušivé napětí, a tak místo 5 V tam je vlivem rušení třeba o 1,5 V méně, tedy 3,5 V. Pokud je signál navržený jako invertovaný, nevadí to, stále se vejdeme do dovoleného pásma (2 V-5 V). Pokud bychom ale měli signál v klidu na log. 0, tak by 1,5 V rušivého napětí znamenalo, že se signál dostane mimo bezpečnou oblast (0 V-0,8 V), a obvod takový stav může vyhodnotit jako aktivní impuls. Zkrátka díky tomu, že logická 1 má mnohem větší pracovní pásmo, je výhodnější u signálů, které mají být po většinu doby v klidu a sepnout jen někdy, použít invertovanou hodnotu a nadefinovat klidový stav jako 1.