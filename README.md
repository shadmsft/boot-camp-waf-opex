# CSA Boot Camp WAF - Operational Excellence Hands On Activity

The goal of this activity to give you some hands on experience with one of the principles of Operational Excellence. The focus of this lab is to introduce you to Monitoring, Autoscaling, and Alerting.
# Architecture
<iframe frameborder="0" style="width:100%;height:686px;" src="https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=WAFOpexBootCamp.drawio#R7T1pe6LI1r%2BmP948rEn8qGIMGcFWIQa%2FzKNoo4jLG00Qfv17lkLBJTGdpNMz03PvTBQLqDprnbW%2BqdXZpv7YX46txXAUfVOk4eabanxTFPlaUb7h%2F6VhwleudI0vBI%2BTIV%2BSdhc6k3Qk7syuPk2Go5W4xpfWi0W0niyLF%2F3FfD7y14Vr%2FcfHRVwc9mMRDQsXlv1gVJgGXuj4%2FWh0MKw7Ga7HfPVaz42%2BHU2CcfZmWRK%2FzPrZYHFhNe4PF3Huklr7plYfF4s1f5ptqqMIgVeEy82JX7cTexzN1%2BfcYN3%2Fr9ov31bSv%2BT%2B87ilrT3r9n%2FyFT%2FmuR89iRWL2a6TDATxeLIedZZ9H7%2FHgOZvamW8nkXwTYaP%2FdWSAf9jshnBuyo%2FJlFUXUSLR7g2X8zhrsqwvxrjb3TDav24mI6yEd8UVZKubm5utr9kcAYIVcTsRo%2Fr0ebkuuUtNIEMR4vZaP2YwBBxg3rNd2QEqFzol3wl3iH08lqse5xD5vZiXxBRsH34Ds7wQYD6ONjb4%2BfRQuoqN%2F83%2Br9Av11XY%2B3ufxl156A8GgLdia%2BLx%2FV4ESzm%2Fai2u1p5XDzNhwRFCb7txjQWi6UAbTharxPBRP2n9aKIqROQg2ksnh790UvzFZzXfwxG6xfGCXjhWl5EzeMo6q8nz0Ue%2B3goX%2F07oXz1e0H5%2Bt8JZfk3I%2BYDQd0dDeBCebk8gD%2BomiV%2BnMxIu1VQfk5ApzX6g1H0fbGarCeLOfw%2BWKzXixkMiPCHSt%2BfBoSYnGz%2BQf%2FknlGOJgHeu0ZEHQp%2FemU5uyplV%2BDzsL%2Fuf1PL%2FFW5WT0H35TKBhCqVL%2Ff2kovqWiD7ubJT5dTL5Um%2Fdu25BuL54Zakf1Z%2FDRQ7%2BYNpR02lPtVrytHg3k7baS1J6tzPTFvx%2BtBXU%2BbMzv83rlbDG%2FbcXNy%2Feypd5H30F4OZ%2FfhQJHXA0VPG7NS0ktKT35i7e6b3017Yf6dQ3WY6KqV6M%2F%2BzH%2B2nKne7FzH1uQa7pKTXt1b%2B2r0NKzfaI2unpqJGYzq8mowty59tTfPzwGepDbmvngv3G%2BU44aK693eUzJnY2l4W75sJCUY7T8NU4vXm5oxjH%2FGZ5qTLXzSgdJe%2BvXStO%2Fk52w%2F9%2BpRjL815vbz8OEu7HV7MP9h1Jjp0bBaqt3XWs%2B%2BAvc9VGDsdG1V9emw3srBL3rqq3boPVSigzXkfstg6AEefGBLT7lPG8rud5ir0nu4S%2Fvd0tP3jrlphLWJWY%2Bm8Mx0OPMVy7ESC9bf7%2BqPvmKP%2Fbp7CThKfCV6HgAerKqmWxMtNatBYhtl2XZaSqNaBtjVtIZTThtObfNXxwxya7ns1UvhYHaz7gFMvIcl0Mz9D4BRAjhaPajDyItKYx92PwAbhr0B77mtaDBXHeYY%2B7cBwKG37D0MqwM1KJlhObCqZdnqaLEVTlPL8QPbAXozTIaXsUz9%2Bk2I7%2FNv7yJfuU%2BGMxd%2BGy57t%2B0FPDN3rwfrH0f97nAxhPdmz%2Fkebta9h%2Fa4V7%2BRvE5l2YPfBt17yeu2x8N6bQP3yXbHBD75fosUuuy0ax5%2Bq9thMxoCbleBP2vPmrObyUC9l%2BCd%2BEzgn%2BUM6GftPbRgdL8rj3uKS1T0l4ozjwFi1mUPsDjo3kjiDmmEmOP3JL0HQUHOS5zYDgfdiO5ryLbU725WHX7XpJFq1%2FiOYT2SBnX3%2BXsYP3uKdXmvlJI%2B%2FNZQC%2BuplnZwcPDO%2B5mfMDzoc1rb2KGbmhPQNZW7ia15zuq6N4tWw%2Fp9IihrBu%2BXgOp%2BAF%2FvRt19r%2FeitnIj%2B6q99Lp6dXC7u6PnDsfDBxvo9OapNdvIfuhtAF8K0EQ6rLdrvYfeEuXHQNGAHkxc1cxUx%2BNmChAUb%2F8%2B8cJRvXYFMmzLf82ZPgY8ToezKBomFcANrBagOVA2zz7Qt5l6CnCKYk%2FMwENegucMiI8AmgBxC2gbni81AJrAv8vBRIZntKWBIiFdAi31lsOqDPi9m%2Fe7GvDu%2FQzpyqoe3JdkNHfkN2mglsXzhjAOn7%2BJ%2FNnNk6e4cL0WAxzmw24Ec28%2FwzsSgB9RhOWUM34mGdAjvmG%2BBnot8LWnAl%2FP7p9gvivvIYpw%2FUiJdlhLrdDC52zlBshvDWh4bRsu8EdZagK%2FwxyWg9kaIHYT95xlSPBJp0%2B2MY3t0Nr%2FPfa6w6gAy2pxPsCzc6DuBfDY8xD0DMygKIdAjoEsURvdHb%2FCejf2vrzajpPHo3q07j8sI6RXq3Ni3MNWLmyajhnvzVuFe6YD1V%2BjXGo4QREuc8DXDOabyCir1s29NY1mpecBrNWuaqlleHLTsCR4%2FrM3W0aeehSvBCdPKa0GqlkyJ%2FasR%2F8DOXVrLwbqcO7PmEe87ibtdQocVS3lNNAyTwG7UYJPNjHwz0LQCn0mvBvTfbw%2FD0BHwVyf%2FYkcguRRYCxIG5fp89aWRt1NJLh81ZxYcrNrSj16Tgv0pxTYBsrUmmQ7ptIwWnIj9BWzbgUNp%2FVkh%2BbKSjTZSsprwCWM81d2R0vsCX53gZZ23%2B1EU5rVODar0oauJfEa7pXsDowN4d7Q15u0H4jFs2rwjuDJdvwV6iXQdTrcqzRC1FkS3K9tmtWyBPOR6D5nCuMsnp%2FBc4PvcL8b8PMC%2BA70H%2BJ3nNvuO84N5hObRg3ux3XCfQaMo3kFq2w%2Bzaomw7gN6B98N84lbRimKuaGc8F7cQ6yebvYybUkk2UV0D8B0BjAdk6fkbcPeADo52kAe6sh6NlG15b9eW88BPnaE3znq20dpD%2Fgp7cc1ONLU2Eq6wHPka7rlFMb9LyVtmQr9FYge5%2BaThB4SRngGMgwZ1hfLUA8ALwTvGYa%2FhOurRGWE9OA9ToIP1z3FPS1BvszwAv%2B7cA%2BK7RSwAH%2B3Zj0LHhHR4N9HeKjpuLzm4aPz99YSZw2UMcYDEt8pp228JkS0MMa7kMagGd5GuJVwBLnseF3AD7puqU36HqwYVhbKnyHZ7dovqDHkE7g2SY9264SfakW0mJVU22gK1pvtYzvVPldpniWn%2FB3X4XvgM%2Byxu9qbfjdHjzbfLJSpHukHXyXy%2FRp4G8%2BwHcaNDtaKt4TAyw2NsAMZAfAuPAZ3w80xGun%2BQGu8Hf4qxDvMK%2FQ%2FGm%2Biabjc2EditXZ8RrB0mnBPGo4ZxXpFvbUwaBKa44tvgf%2BVoAnyoh%2FepeV0LsARmWck2qJOQs%2B3SCu4a9mJzxXmBviWmVYmHoD4A2yMED%2BstIAcZ%2FCPAFevka4d8wAngs8EgMvBKppeDB%2BumoiHqqAa4P5ScwxRlwTfRggT%2FAawwTkBtKjqwoc0frsMAgQ3kCXK6DxDckekM%2F0TMA9wyTA5yg2w0Hj%2BU9lpitLY7oydV5PIInvJNMsliUoh3JjLKRFmMNU4%2B81pH8Nvgta9VEmoVyISZ51iI%2FE%2B6YSwsQiegFeSV2UmamYt8K86PO8Ux%2FXhOtn%2BjdqCHe6z0Iem2gCBzW4z4N18noBliumPeQj2MsTr1kI3xTlGtCxTDwCspTg0qF368AjKa8bZHzq4bsz%2BpRg%2Fbg%2Bifm2hffhnBEmEj4faAWfS%2B9CfMM9YHsIfOGaUpqvBs8DuJkgc1okS2i%2BTkD81NzRwBreDTRONJST5yj3PaANmB%2FhsKyzvKntZBPoH8EbIJtJjigNXivOKYU1ou6Q8T7kGeR9oAuAoYufdaBbmejKsVAPSLAG0ikm0UQtaeC7Q5JXG5aVLskbnB%2B%2Bu8lzTgjHIdG9btE4T0KZCvJ9xbAmeClCbiom85CQh0FgsaxE2CcwFvAyVZnPApoXr6MMz6zFgjZgPTSvFGnV5PcTXG2GSyJkTmwxH8uCj1PWoybPi3S3iXqS5tI0PIEjV8ytxrRptFi%2BMk%2FpJFsmglc7IJdYfm1QPtlVehd%2BR5wgblX6jrKkw7zN8pV5Duw2njeP1XAPgM9oMp2ynqiSjGG6ZXyrNr87bXbEs0kGwR5FyCmkG9gXCT3P%2FCBkm0p0nbBOaxLfuEIuuDrjZirgAbjZyeeE9hZEvxbQgBfYJLNJfmbzi5tC7orvJPv5L31PxPwTpomyzvIwCMRYpDuF%2Bc5d8bit%2FE6Zv1HGtvDdCGfcb4B%2BnRLPNVFHJ0LukRzydaZlpFGL9gHMK3ifpxT2KWB%2FkZ8lQCcV%2Fv%2B0P%2FAgdnAyUCDL0oWU%2B0eWC4EDpVS60A8CB7p8GDfQP8AHeDRacyQ488tcrXtu0J%2FzvSrn%2Bl61r3S1KgeuVnKySp3R4%2FME1qdI36P%2B%2FN%2FmdQ0LXlewM3rdG6n%2F0EMrcT3ooseUvaGDOcjvyUd4az%2FM25jNBT2zL3hTa6itn2H39gwrWKPnrPFg6zC38agq73mEd96c%2FNxyHscn%2BAxrtSP0o%2FUUFy0hqSG13XbePu6ARJu1pV71l3qItQFa1%2BlrHu0Sj4P3FLyvoKHQO4EWGnlqjGkMO4A9j0Qv8ue28IzRzgq0VHkBO5AYNLQE0h6tUthZS6DVccc5RSs%2B5yFrP3sKesnQOryJ%2FZtS2gOrv9%2B1owe1svK6%2Bls9tYnNmjVhay5vfd4D7dyteh154nXtx5569zzs6tMmesVhJ4YaCzQY7CRa4q91xbCML5neXLSC0ScKa%2B5FZphpoc0pP8jWq7fzsFjs8QvRE3wHOGhH%2FqwUw3yWw9spemUOvHrwDAks6zWuGeYz6z%2B0gA9vgNaip0Z3E%2FXmraPeQH8Wzfu3x3%2BD58XieeThge8rgPt4AHSMninyEqr3S5j7Ma8Re6jRy95tA67uVaYNd9%2BbI%2FvzO%2BB5mG%2F9Ru89wPoRl2lLh91DeuDRIw8bWh6eBFaqctTjh7svY5raYPH%2B8fjtPH4AM%2FRWyAAf7Ys9fte9zGPPeEYZIuEcfAWjUBLQQBs9yCnQhNTrBDHvYsuxbbiSZbjLLV%2FF02sRNxAeqPZyWN9ESGtg%2FU2%2BRxWMMYA1ED%2BLcQV%2Fv893zYbJQL2Hp%2Fuwz5XOmU2Ke9ym4ad%2FFVZfdTagB9sgP3h94p1g%2FZVhJ40jWw%2BV2Lwh6bAEiAd%2BfTMGqX3dUHnmWYyg2ppuoeQrY8SkBHZLDDYFYIHnQ1EZwOzwFrhybq%2B8h3b0l1EWdmRZsVMT7IrpJPfMu%2B%2B3%2FB7hZ%2BXZOoiFVmyGutOv30dD9DXBuwCX4vcttHGFh35a9K9jrOt9ftq07dg3luSiRMVn2xbZ8lPZS9lmEraexjYM2e9gDyBlBFLfqKXk56uWA7NaCWk8%2BgmM7dgUfbXkG6FrbQXsJ5AUbRhL%2FgSV4Jb6%2FNyqlB9r0jXX4vcbpga2GPpnVlboo30J98Tov02b9x7NeTQxn%2FO4bCh%2BkU7mWZSzX0ceb6mWUwMLEfQrY5OicoghpsTNeFh3F%2BRBMlpknYFeRs%2Bg0jwfw%2FIehjdvw7D%2FXgxv2s7NjeXmMYweuRj1sNTsWoittbgWM5bJuwG%2FI1bBWkzLbD0KzAL0V4w9U%2FXxtw55dRFzKns57kL0cCOmin8r6daLRhj2yEthzSx6Lz%2BXPGiqmFNiq%2FgbPtMVHjiy9uWM4th6RutWIgqg%2B9jLGXfoHcPLQlQSIB0%2F99Id5LfyaA4aCCAMEN9YE0l5RR4lQLu6DfyO%2FodmR9NQI%2B3JpdZpOWk7ZZCT9qLXhT1piHRoHpNGd0c8%2FSjX5H0d%2BWZPv2RqbaOVWuGKIzRTgLthKgDDVHC%2Bwpzragz%2FgGmC4a%2FlOF4hDyfhnTxUyvYzesnrRF%2FoqWfPGnmfrPXOy2cbeB3elbDHAZ%2BFkRBPZU73AL%2F2z%2BAwkbTXcWjSjqbBsaTYDg90y4s4dPdweFSjnMThu6M1KfE18HcOh8SDpozUyXybXdvyeIF%2FMj4mWBd4HCwYwpWZMK%2ByTABe1cjjWY2Lf29RSgeKeE7Gp4mgpSSTLXke99MyeylZmyiCz0nmmHVry8eHPF5hzaDmPE5IBdXS%2FBVNLsE74rdwNtksgKs3UEW4z9mtt1CF8oezX%2BNsoJcNQul8nY1e57JqJ%2BfqbG9fZ8tv0tnh5%2Bps6wWd3awWdTZhWkRMBa9rmc62Czq79yadbW91dpDxs5bp7OZtprODvM7WPldn41vO2MkBj7XiHVWAdXz2Ts7f36srb6KK9L17dbvarLUkKzXze%2FUE412WwtiwCRvIcwxxxixjLEcZMG66EtI95Rhc9hnHj4VW8CURF6a4LGOUeD9tpSI2GgZCNtA%2BXGHtwbLmZ%2Fbi%2Fpoy8V60tCiyChLsbKwhLxuDeknuVcuhHR6zSXF%2BPkj%2FflVoDPxs0N3qvrdjoOhPva4tgZW%2Bxtyp4exGAtxFwmuTDm%2BjFcpmzD8bGIvQdqKqXWvpzYRzKhzHjEUsF2PaksdaMGUuqSUcdwsori4%2B7zQixYKEJnU8wXkWaGiS18gDKNcV5vgW5wcQl5sS5zT0QuY6b00xVYrfuXLD8TB2vKY4UNcSv%2BF73Ew%2FoG2mcLy4RXHm3JykJsc4FZJEjitiUpT3kLKUaIdiLThn1Isr2GPTXxvvv8U1tDjPB77z5%2BECvUpWOjbQ6mpm9IaSgzyaLbIDMb9k991Fu%2FFl6VGkxP1v6NdNtQ%2BMWRWDVLKE5S25IJZyGLGSjkSspE%2BKWH1locuHRKzUMyNWvypgdRzKh8UB%2FxGwX34p2L8EygDLx%2BRB3E9fvPwXY1P4luS%2FfR89TmDpo0dx8QsQpn8pwtT%2FCFvIpa%2BMn6sH0shazCfrxeOfkPmfkPl%2FI2TuoGt9%2Bpkh80s0Ch4UGYw8MDfUOzAi%2FKdsTbswOYaWK%2FEIDVcsRpHunincWsWwt6XC5nyz%2FZs3Lrr62Jttokb3DmhnPfdnJXkwa10CvlQKl1fLqY0J9R3xF12ELxRF%2FSmS2QZMZXKvn1skc4yOuEgGnV5grAcSpxQUftcp5NzBxHoMz%2B%2FTIYZP758RT2DG6sKwPAipo1sTw9j4rlOh6379ftlTxhKlDhi1fWN2O27QvdH6XXk5mt1PceypcUMFUxIwpaOmWwTzoyFx7VhIfBd2B5qfSPtpApcDhVIpMPlZbYLZznAtTfro%2FLw9grtbgtOOHnPFCwCb56GC9ICB5t54cGtH%2BfB1vhizQOfbBMate0Lg2H%2FZLcGJkVLTwFB%2FVpzgppZTS0B%2BvB46dwLdfnvo3PHR9H4tdE6uHdvI0lnd2A4D5awQugy0qWYhdCzZdAMHtCaMhPcANtOjzpSda4fkkm%2B4mIayLpb9nXShAySaRnnyfeanTaMmnXCx7TmP4A0OOhFfcf%2BR49GSRIpxbKVWYu85kl6AhMYrYOeQpQJ%2Bjzr2jzoAaVWt9zoA6%2B1pD%2F71dg7ACRamUAhG9xIsJHBlctN20BlKxSoaOYQcDNRjwQ4WeNQ2Zs4ZyAn6eB8WSXkrSuXB4gIsjnBqK4KacU%2FuYQ7VTLMx6yYnaG%2BshJICNlT00WWnkE2OnppMjh%2FHwmRp3Z5I6PRi56vTMyx0KiaxTkU7hi%2Fm0tIpyT%2BlQg85m2srtSjRnd3SFoWS8DPcn3BSMs4%2F2nf%2BHLoeD0NDMqxl03DcV1yP6Fzy1SYXkqHjDHi7kBbzClX7k%2B8c6Ent1FePUvZRR6SrNeH%2BdzsiYcfWcspxU6FA0XqnqxeYiLGlKcBnik64ATkKfZmKczKHX7ViiABSSgUTCTn%2BNoAPZRtGTKcw%2FgYdeSKhw90IJ6dIJmltuGiDHIugB4lONg4mdKRAV7fFsN5pmEz39dQbYbJ8gvHRzjEr3l%2FngimgZ0xuUcnZjU7QFIs7fErAtzoxFsaJcKmlU%2BGRoNMB0C7wOgXFKFSDjldKVoH9QIcKhdgx70yxOAGeVXCU74cxD4Mdji9bk1eD2xsqvHJckvpYIAl0exjGPOE4J%2BhKZqiT9LJSpPoTjvNjgUyUlrr93kBmOqy3pjWwBdYk%2FxrdbTrmJYaVdnhrUXEG7LVAuo%2BxmCYGuiTa3ckOlwpPCIchF0Bh0RI6ugUOEyzKGlDBT41pt25xEQjSdDYOaRdlExVE1HTHKLz7UPachM7%2B7uit0BnMSk%2B9XeBfwvImWIXGqyCOFVTMEDBrWE7akmBMyqVNWFqFEDE5eMjQ0Jt1Cg3TKpuYpkVllRTWEeOQirG0qSa49yeol6ynl3V1EwPvhq9TeW%2BIoQP3fOrVwX7c5KhXO76fOokfkJL77S8%2BmHqVHfX6WH4HePCIejnkhklpVDaZ4U7iMA9Sqauj9GgaLlEzhT0Ad3YHtGs3ZolN%2BO%2BF1N4ioRLYlMrKUgrP465ASHYsZRtaZCFOSKLpzfOkL0JY%2Fljp%2B9Vw8Ivr3gs5H99zgpR3Wq%2FsGjwsRxW7BkxbLKv76aEn95yorav5PSfsf96w55zGwsZ9TyqC2p7eVQDbV4S1qry1S5tU1L5LUWB9D1IE0wprJFM3XNiaCzyjBAHZy5gzVzYXBaec9InFuHcsvycsv70Ma9SQRWCNC2lTUczKUu7e4%2FeeTb21fZv5ndTb4oTXFHX92LIYDjqlV2KSK0pbSooJgHpdDt4mBC91l0CLewdrt6YurXdHuRTAbYnCa4RBWaHGBKn7E5SLNuYrNi0XDcsw9sw9LtKbm9vjBsfTZk7j5N3B9pZTqVhuLckF23GfjvDHVHbFo%2F2qm2KxKOxw1kRrVUlnG8nj4DUXkOYD3KrYx1LCFEolLrzP6BCvDbmolZsgpJxkQUlTqUi5SzhZiva8arPDCRceSDs7tZAPUqYFstFkKgxHmkH7KyQpF%2BzSZ%2FA6FQ3D%2FhOD8rD%2FRJpKPWFXtfB5mkc04sucDDDFwlLUvDE1VnACoDOXEg%2Bs6W4P6%2BHeHewumxO3E5HYRQ0aYD5YuJ40nGnRHghBwqG9iAlduM%2BlxC4Mylu85wo9LhhHeWH0ftY%2BQxtWP7tkIX0DzWLC3o5m32KXAc0e%2BN4%2BgGbRjrXIFrEcO6TkDMZfCraSyok5RCMaN5MAPBKNbHES2pykr6BsaVCSPibw%2B2zfEx4ovVKxFCq0p4QPS7HAnqedJD5fw%2F0tNxoAuhKJGrAnpiQR8jlgckiK%2FoEpNRzAphNY2E7F%2F9Ut%2F%2BxSSJFmudAY5WDKRcR0TWp2c%2FOQrI1IPkRtrgD9MX8aqP2nwk%2Bxhc%2FP0hPwgHl%2BCcyb6KkgA%2FU30tO7ZSD7iHr143b%2BLnlM%2BE5SskFz8s4mPKKfBmQC0gzqHMS1E3CDEZB7lBCkID4CSh6ihhvcxAP9PIjjhBoykB3mpQMsoGfbNyU%2FFdls%2BNyA7GCyxyZSArjGpCBpu2cg%2Beaib4foH%2B2uJu4ByOfj6ZxsZmoexuFEIwLRXEHhPYaFclJca%2Bn5ebSwsIeegZYR0DwWvgsfAKYnFuCzl2p8no4FeGEDrRd1rIn7HJ2bJgC%2FhdPN%2BT4lLLfKy67p8dKSk7RmvVt2bX1KW9llcYMRsCrtkPdBQE9Sjr7QT56KxGFKJmRb2qNGFJSYCDKiCVYYFnu1QD8KywQbDSD%2Fb1gOWNykZveun5UDKOPkV30pSPeOu6GUcJKtZ%2B%2FgU24QuN3BnygSOLmDT9%2BbTGzX2myv5ZOJsS0LaHjQKLzD0Th1ELmZkom5bQ5Lv4Q8gJ08BtGDh7t5wXE0zpMJg45HKeY27XxdLWsrI9qSxNQupEOtVuBzb0Ee4BkVD4ix1E5F4V2HlzBV0K5Jth4sbl1EGsSTxG6Mxuc0DqVJkqfR4fZTnCaJ7S4qJrUKU6x11u4EW6hw2mJtxe0sKG2RW9M4kSH8HzA2azE0JW8PcNuqAMd9y%2BMcCRFiy7JXd%2BGYdqlT6xLaoQZnSwfbKEiHN%2B7GW%2B%2BWDu2pp7XSvHSoIQej5lex3VYH2%2BWkVm5nizRVo%2BgB48QX%2BEacuJyOHN4YTHMkFTTCCT3P19n7HHH6MheiMM6oLcrNAuFnuxZys8y%2BMpgP7bbRuwuaDrUFWQaW%2BH73ulT5wuRSVVELyaWaXrpQrn9ZQunpPMtCblFjEWAb5Hk%2FStYTf%2FVvyzH60wz5390MWQPNcOCt%2F8hmyLA%2Fx3wVCd%2Fvy6U1aALMa1j3urr0oNoySOzoQSmt%2FUTH%2BcD6g23OEOXZcOsNavfQmpUotwhzgECyojaNyRdu%2BCk1knupbcakomL%2BTB8bIO%2FuxXYQi143a1nBz0G6gN0jtTqWI6CsKVDuWEAt1yrYS2B3hi2PkQov3Wm7Dp%2FBHlg%2BAMU8imbGY29WkjG7B%2FTadaHx8SxaY6YLU%2BAaZ36NXNWcIaXI46EhmhjfRjHsvOgd%2Fuw%2BHajY2MPNU2oMFLYSlDD18F9FXvJ9JQf052pQ43exvP9eh7cITYqtkhvKtqEzt0POrSd%2BzrWE5nuj3twSmRr0GYve45zWLjTzrHb4b6ZRCg1a%2F4z9krGA4SnIo3SbF1cHW%2Fq2HfkihzBrLv2A1J3t4p3NYcPq7fj7W%2B%2FhPgWZMR5M71bDB1NrGlNsHo6RI6Cje%2BBflgGcz3Vd2EWIt%2F9pbLNtbAPQQ%2B10ZmObQAeteNiqmhrJUIvexAqDg%2F0uSlebS%2BgUsGv2G%2BP8pxvbULvC0I9hj678Jq2sE7RNhA6iz00j0MF2FBrTR%2B8UtWS1M82ZkseBNeTx0r2JXW%2FpBc0ItrIVcmvXombECJApWr7uYuIZD%2FsYO85sLPxsBJqAHWpsFT203K60JbKCKZafiucdiS%2B7ugcWFv62y8oszCHIZX%2Bipy4R7VDPaSeN0kmz35mjkJ8j2X%2BdMq5Tp92Dwe2kge%2BCTrW8QX%2BDFeL1WnA%2FKSfY%2FpTbg6MXj2xznVoWY8tbGleWyMPn%2BNT6s2lYeC3mVrQ19XjbbNhhqy2xTvqM69SRL1kWoFfSynCr0xER2JqV5mu%2B3OZ8d6xEAdaFYyUKtHN9FgUTdQoKRuvZ21IESSfMU%2F%2FCmQUvzAxLg82v4i2MJma8hR47xUrFqom3Whg1S4kOJ5%2FNW0dozkH6FjS3lUWYQbSlvS%2BAF3mDT8giD%2F1zydfMqxVnFRO%2FD0%2FaW8ovfwFFHZHW2E7m3fl2RWk92JPWNklrXzT%2Fd7lxdFjDBtEbO80kskljCKrba9hM3keprjTJM1sxqaF1OmWJPan0j0L%2BwB9OkA%2Ffm0W9dzTFVArIx0irLCsis1O2aJboCwyyWSrcPj5IzXrArc5h9V6Sle9TBFO0%2BW8lHJ0wubW94%2BlZK3KCTFK5fAOtYeOIEzsYmw6moBl%2BPnceeImRO4P93eXPNEjI5kjeA4A6xsRUwkgnVigG3KksTGMLcYwpr4T3PxAN%2FtdEh9zYWm0UMIW55EGQb0jxssQJtNOa41fuyo5qDsqrJc2RUuN%2B4jEhGRWM5HyN%2FKnF798tDmferBaTJcjyR6JYMnEm7gArocnxN9zl4QEwCeW0dOggFYka0IeuyJmBv9iMHQ8jwYNbqrEYi9ew8QbW1WGEoLyhyM6EGt%2FLLNfKATWewGgAt6uVqUk95XH7QfYOjBtmz2lQZKOMDfFpLhSt4Tms98afT4dOLdPIHIN2CA6CDtFPGain6dADHq%2Bp3nn4JjoH%2FJ05LzPTyBLlqZGcz3YKGI9Hq%2FBD5qXjIS0smVtn8kctaYqd1Z5spJo7G%2FO9jIyfDzSDAvPY2ErtrJ0D5b0Y3umdwzH9tcEGqR99tFJOEgD1%2BgllUIDthFka4ugW3UR9lLLUpOMGSA9lUpN024aOsRESE49lOZ9SW9JpinDx2B7t6%2FbaNdk6LTG%2Ffi%2B5scPMvtvxNHqAvty%2B2%2Bx8J4f2nQU4yu0i3r%2FzcIJz8aluNSDvSPP2%2Bi%2FSgEfnpW1tuiPzohZ4YSbBvwKbTcc8TWe%2FYB%2BJvrzhDP12HxP93h5BL6Lf%2BtXVYej78kjo%2B%2FKTupcoh301%2BKB6uG%2F%2BDU9%2Fv8FDKsSlxdMaG348RaPVN%2BUygslVBo%2FwKcBP1e8u%2FPi0nkSTtE%2Fxb0Ua9Fej4Zc2tJELDW0uFP21njabyXp7H3z2ctd3t%2BCX%2FB2f2ARHP7M9i%2FKV3Vn0AyoqA0pWQDaTeXCA%2F1ezJXKIPJEVIb75AE4EemW1flxMR1laxXwxRyr6MYmiXKaFJFVqNwoOFtkbs03w2F%2BOL%2Frp0%2BPooi9mPPoYVtcUvcjqJfVCP%2Bycdnkk0UVVP6tXkf4P71V0eSYzXH9lRyjl8oAbjsnGcgS0dJhahHAixigC8YDi9xljNhkOGV%2BjFbxkQM9DjC0Xk%2Fma1qhXvum7NK4DUlYkfzGfj%2Fy1uBmuSYeoeoGwTvKCdCHpJX7U2SgQD%2FuOs88NWfz4sQLU7%2BNo%2B86fl2GHWDuBoYOUrByaDoF9gLgsZ%2BzHYr4WPCMruTSuyQwk5k00GcB%2FSTLhUmf9Ofw6g2f8HSwAc%2FP%2BHA%2BNuuEpXmCu14dILV0rblAuJelAZGlXR0TWLovv46WW9qU7iGJLvIur13YQHyjurs4Ud196stnVId%2FQyWbmfIX08Zvzz3IZgRRFkfx3NuGP4yZZvi5wk6ZfX%2Bj54wAvD5hLPbb7ly90%2FbOU1fU%2FfEtwfcgjxxd69aV7gtLhnmAx%2FzHBNOP%2BHEwkyRgto0Xy79gOKCf2X%2BLx%2F5MuVP16r8nw7749uD4Uc8PZZD4By6N%2Fog3lcBELoA%2F7q%2FGWX3JoPMds0bSSToOjPXPpAPcn7akzjSgw78Feg%2BkQ2sVs942l59GoP7tYAtP3o7%2F7CIKPkZWXenHnoZaO7Dy0C%2B1QPGrXF5%2B19finC8esm%2FCrOwj1K3cQ2SxzvGVM%2BsF8sQKqRfcTgGsyD37vncRuxqu%2Fswl%2F3E5CUfe4Q1IvtHxPdu2snYSmXkhXn8QrV%2F90XtH%2BEbxyWKz0h1dedrIrR2zYT2SOF5pnF%2FtXw4P%2FhbVlf%2FpX%2F%2BlffbR%2FtYV15eFB7lW%2Bji2mXi2hFfxlmHh8q4w9CE0D5oZ9CbD%2Fh1NbYqwvl18%2FHSg24RRgofhy6Xkw28Dz738MZ1E67N6ssPLgQa0kA2WIdWNvPQJasqnrVjnlvjhvOwLaNlzsdRRYKR0Y%2BucI6DMrZQStHFS3DB8wNqxLMM%2FxqHufiHrHDdCG0jysrOE8JDxs1aklQEtHe1pTdX3a2tj7vW7%2F6z2tMfpPWSbBb9HTmmnCf62HKPe%2B4gyiYte64%2F0uiHasNHjzEdAm1fi%2F2o0Hu1lxp%2B39XpAvzIe6IEQ9x6yVnlC29jrltXnTW%2Frq%2FRi%2BX8I9LeDzOVaO%2Bq91tM4OK0tsPOrwrI7WDOtWkj88zgLNfqKz9UHuhrg%2Fy7DKsuAT7JtkH82xqyl2aldb1PN%2Fm00i07GfhTwNzF8z33SEpkVdN17veHjQL%2BlF%2FPj5AzMBsqcOzDzIuhH3T%2Fdz8bG38PH8PueuAtC9KuSx0BGkheyfBHTT2w6vg1m7a%2Fu1Qym5Y%2BL5kHHMPcgc7zh%2BEjKEqTxkatg3JT2W4WO5Ndkyoir26thJRDz%2BzS1mPfIa3ko1CtUZvtwJST3vkFXmB1fd46dThzGe4CdX3%2BMnzN4%2FRjN6K3XjphO8RjMpH3b%2BdrrBQw%2FLr%2FWAwRzK8%2Bkm3Kcb%2F210E%2B7TDULH0o7STdozbLA3XqUb7N3SeTt0sFe8%2BQp0rPSIRniRerx96tHeRj3eAfXgEeDNo1ntNcUC6d1%2BVRrXkrceeorH0L9%2B6KmNnYzOOuS0Flupp7JWc5Vx1HvAYxjhLae6Jx%2FJBuZnHFS3Ye489UL7af5K6FDJFykoL4f2Pn9o5qGaOY6ydKRr9UI77LtzecIvon2S0%2FCIXwQzx2b9NeYNSt3RADNlMJ68n27I8TL0LR3Pofns9IAsT%2FBCAsjmcgUv9KvLl%2FMFTyQWnJWa%2BDGJhkdRkXmYXz8I7p3%2Bz73QXRYULF1dFDPm5Ou9oDcvQdz3rgjf8ajll2TH%2FeI8k6MrPzfH9HMwL0t7sQ11r9EXz%2BvT8H6YvApYjVejozHdP67ZP67Zf51r1nammmW4n3i04F0yUIdp78F843GCgUaNMQxfFa3A3nKcIGxuqbxWpRK6P8cJvuE4wSDeb%2BjzwnGCh7TDrle5iS64NNiwYXXgepWpCD2EbbKzT3v%2Faderhm2Em4aVWOFvc5wg4PiVttBUjOmBbJumDf68aRrBpmjinjr8xk49DczbFrXOc2qHpv%2FhAX0JH4nyivuqo4EpW9apbHT7uWBYnmpFiyWhk%2B%2FTreQ65o44aM5shZbUcMwzDFdcs5%2FsDvyxjjfxP95iGeb2AS0lXFNqG9Nci%2BVYtbGpuYKtjcsbblVEDa%2FlJh0741KLCGpkj8fvzAKND5XIDkupbY%2B0obHU7CDgsdRU3U2GE0lGQ7ljVLo2HSQx3G9X%2B5oLwTGxnbt0Rht8mdpeG65%2BnpuF4bo78M5KpydcUMeOX%2FLV5v4BrG9tJiDV4pZzU7HC7RFZGhe5xyhJ46YbIAxTPmBmiu2e1xYfg7ThttU53EwYJ0NsIR16Wl9o0ntsWg7%2FtlL6rjQAOvBdbRiBQs8wXJI%2B8J0PVRDf82XV57jBkDu9153LVeJK3TbKiT05x92DXBPkuKZ1vH38Ca75yOMsjx8ttMUcYYqPzQmyg6A2fAAUXcsaPWPrAQUbP6OuHOKRkmFZxaNYRANyHbAv7rP4sKmEW%2FwjN%2FXxOApjbCEn4dGEeDRRs8ZU8jMY80ljvRwOoCPYNDyO1A7xcJ%2Baap3lqCPMoQuTXZJp6%2BxgEmNuP2CCTV1bRwt%2Ft4dJFN27QOetvcawBLW3hAVQvuOBOvEr0gcPOlGx0QJKITwWDtZ7jisc5YheOLIVVn%2FSkXmkBbqdTqUPaG5TtWstvdgCHQ%2Fl8fEIPQ2oc0UHtZJMD1Q63CRs4cGqKKtQ3ojDMCopHtpDh2bgwVF02CsG4%2FBaO7So4Y1PhyJg%2B%2F78%2FbsxWVt0%2FFsxLGr1D5RODUpccahrixo92cgx4iBYmw5aOThg4Qzdgu5p6xW5xfYEurKRC7BhvxVbZ8uvKXIB7Ls2eg80BFDGmzQ%2FF9Z%2F7JG8sJ4EZIqG7mrQMjIfbQpYTvG4nB7JFYuOPJ0ClZl4QIE4uICacYCdhcdclJU%2BHUdyp9CRZ1OUQ5bsYNus0Fo16Uing6Nu39eK%2FkjRwoH%2F63QZwnXpopT%2Fp%2BghV6%2F0iyMFOtfXhx7yq8%2FKqVW%2BpPTtAz2LRwp2T%2Fvgvqo457Dy012NHn%2BPFNrJEG6frGGRNzSpQprs%2B8hf2a%2B4uLq%2B0A8J%2FvJIycXVBxzFcDwedFhmc4CG37R9AP7379XTYOU%2FTpY8pV3dj%2FwxOLtUiijLIiR5%2BXR1oRwi7PLT6gcPyz%2Br0eIJg3edMd3%2FGzDR8nH0PBnFWO9JWKIZ%2Fk3zE%2FxUQFSRGgj1Vzc3N9tfugLayh6RCLr5ADzreyERKgE95Mwjqkj7rFKoLCiTQ3R9sr59wgBte7Rc%2FEPYNJisx0%2BDv%2F3FcJQR3Oix9jxiupM%2FgWdBzhargLd4y6Hy6kgbkJ8QsvD1cbFY5%2BNjuHYLVosj%2Fh8%3D"></iframe>
## Objectives
- [CSA Boot Camp WAF - Operational Excellence Hands On Activity](#csa-boot-camp-waf---operational-excellence-hands-on-activity)
- [Architecture](#architecture)
  - [Objectives](#objectives)
  - [Prerequisites](#prerequisites)
  - [Deploy Azure Monitor Log Analytics Workspace and App Insights](#deploy-azure-monitor-log-analytics-workspace-and-app-insights)
  - [Deploy Azure App Service and Web App](#deploy-azure-app-service-and-web-app)
  - [Configure App Insights and Diagnostics](#configure-app-insights-and-diagnostics)
  - [Configure Azure Alerts and Autoscaling](#configure-azure-alerts-and-autoscaling)
    - [Alerts](#alerts)
    - [Autoscaling](#autoscaling)
  - [Query Logs](#query-logs)
  - [Reference](#reference)

## Prerequisites
1. An Azure Subscription.

## Deploy Azure Monitor Log Analytics Workspace and App Insights
[Back to Objectives](#objectives)

1. Navigate to the Azure Portal https://portal.azure.com
1. Click on the Cloud Shell. You may be prompted to create a storage account if this is your first time to use the cloud shell.

   ![image](./media/1.png)


1. Ensure that you use Bash for the Cloud Shell

    ![image](./media/2.png)

1. Set the context to the subscription you want to use.
    ```cli
    az account set --subscription "<your subscription name or Id>"
    ```
1. Create a Resource Group and Log Analytics Workspace by typing these commands in the Cloud Shell.

    ```cli
    az group create --name rg-opex --location southcentralus
    ```
    ```cli
    az monitor log-analytics workspace create -g rg-opex -n la-ws-opex
    ```
1. Run the following commands to get the WorkspaceId and the Workspace Key, alternatively you can get them from the Portal as well.
    ```cli
    az monitor log-analytics workspace show -g rg-opex --workspace-name la-ws-opex --query customerId
    ```
    ```cli
    az monitor log-analytics workspace get-shared-keys -g rg-opex --workspace-name la-ws-opex
    ```
##  Deploy Azure App Service and Web App
[Back to Objectives](#objectives)

1. Deploy an App Service Plan and create a Web App
    ```cli
    az appservice plan create -g rg-opex -n asp-opex-1 --location southcentralus --sku S1
    ```
    ```cli
    let randomNum=$RANDOM*$RANDOM
    webAppName=waopex$randomNum
    az webapp create -g rg-opex -p asp-opex-1 -n $webAppName
    ```
    ```cli
    webAppId=$(az webapp show -g rg-opex -n $webAppName --query id --output tsv)
    ```
1. Create a deployment to the Web App, using a sample application
    ```cli
    gitRepo=https://github.com/Azure-Samples/php-docs-hello-world
    ```
    ```cli
    az webapp deployment source config --name $webAppName \
    --resource-group rg-opex \
    --repo-url $gitRepo --branch master \
    --manual-integration
    ```
1. Verify the web app by getting the Url and opening the web site. You should see <b>Hello World!</b>
    ```cli
    echo http://$webAppName.azurewebsites.net
    ```
1. Verify deployment settings in the Portal.
   1. In the portal, navigate to the rg-opex resource group and click on the app service you created.

        ![image](./media/a.png)

    1. Click on the Deployment Center

        ![image](./media/b.png)

    1. Verify that the Repository and Branch are set.

        ![image](./media/c.png)

## Configure App Insights and Diagnostics
[Back to Objectives](#objectives)

1. Configure App Insights for the Web app
    ```cli
    az extension add -n application-insights
    ```
    ```cli
    wsID=$(az monitor log-analytics workspace show --workspace-name la-ws-opex -g rg-opex --query id --output tsv)
    ```
    ```cli
    az monitor app-insights component create --app ai-opex \
    --location southcentralus \
    --kind web \
    --resource-group rg-opex \
    --application-type web \
    --workspace $wsID
    ```
    ```cli
    az monitor app-insights component connect-webapp -a ai-opex \
    -g rg-opex \
    --app ai-opex \
    --web-app $webAppId
    ```
1. Let's verify that the Web App has been configured with your Application Insights you just created.
   1. In the portal, navigate to the rg-opex resource group and click on the app service.

    ![image](./media/d.png)

    1. Click on 'View Application Insights data -->' this will take you to the Application Instights instance.

    ![image](./media/e.png)

1. Create Diagnostic Settings for the Web app
    ```cli
     wsID=$(az monitor log-analytics workspace show --workspace-name la-ws-opex -g rg-opex --query id --output tsv)
    ```
    ```cli
    az monitor diagnostic-settings create --resource $webAppId --name diagWebApp --workspace $wsID --logs '[{"category":"AppServiceHTTPLogs","enabled":true,"retentionPolicy":{"enabled":false,"days":0}},{"category":"AppServiceConsoleLogs","enabled": true,"retentionPolicy":{"enabled":false,"days":0}}]' --metrics '[{"category":"AllMetrics","enabled":true,"retentionPolicy":{"enabled":false,"days":0}}]'
    ```
1. Let's verify the Diagnostic settings were created in the portal.
    1. In the portal, navigate to the rg-opex resource group and click on the app service.

    ![image](./media/a.png)

    1. Click on Diagnostic Settings in the Monitoring Section

    ![image](./media/f.png)

    1. Click on the Edit Settings of the diagWebApp setting

    ![image](./media/g.png)

    1. You should see the settings as we created them in the CLI.

    ![image](./media/h.png)

2. Create some load from the Cloud Shell.  You may leave this running while you complete the lab.
    ```cli
    while true
    do
        curl http://$webAppName.azurewebsites.net
    done
    ```
    Type Ctrl+C when finished with load test after the lab.

##  Configure Azure Alerts and Autoscaling
[Back to Objectives](#objectives)

### Alerts
1. Navigate to https://portal.azure.com .
1. Ensure you are in your subscription.
1. Navigate or search for Alerts and click on it.

    ![image](./media/13.png)

1. Click on + New alert rule

    ![image](./media/14.png)

1. Click on + Select Scope

    ![image](./media/15.png)

1. Filter by App Service plans and select the asp-opex-1 item then click Done.

   ![image](./media/16.png)

1. Click on Next: Condition >  Then select the CPU Percentage signal

   ![image](./media/17.png)

1. Configure the signal logic, for the lab utilize the graph to make a decision as to when this might trigger. In this scenario, my utilization is pretty low, so I will set it to 2

   ![image](./media/18.png)

1. Click on Next: Action > + Create action group

   ![image](./media/19.png)

1. Create the action group. Save it in rg-opex resource group and name it agEmail

    ![image](./media/20.png)

1. Click on Next: Notifications >
    * Choose: Email/SMS message/Push/Voice
    * Name: EmailMe
    * Email: [ Use your email address ]

    ![image](./media/21.png)

1. Click on Next: Actions >. We won't add any specific actions right now.
1. Click Review + Create.
1. Click Create to finish the action group creation.
1. Click on Next: Details > Setting the following
    * Subscription: Choose your subscription
    * Resource group: rg-opex
    * Severity: Informational
    * Alert rule name: Alert CPU
    * Alert description: CPU Alert
    * Enable upon creation: On
    * Automatically resolve alerts: On

        ![image](./media/22.png)

1. Click on Review + create. Then Create.

### Autoscaling
1. Navigate to https://portal.azure.com .
1. Ensure you are in your subscription.
1. Navigate or search for Monitor anc click on it.

    ![image](./media/6.png)

1. In the Settings Section click on Autoscale

    ![image](./media/7.png)

1. Click on the rg-opex App Service Plan deployed previously.

    ![image](./media/8.png)

1. Click on Custom autoscale.

    ![image](./media/9.png)

1. Set the following Values
   1. Scale mode: Scale based on a metric
   2. Rules: + Add Rule - This will be the scale out rule

      ![image](./media/9a.png)

      * Metric Source: Current Resource (asp-opex-1)
      * Time aggregation: Average
      * Metric namespace: App Service plans standard metrics
      * Metric name: CPU Percentage
      * Dimension Name: Instance
      * Operator: =
      * Dimension Values: All Values
      * Operator: Greater than
      *  Metric threshold to trigger scale action: 20  (Set this value below the CpuPercentage in the screen, just to trigger an autoscale. This is just for demonstration purposes, you should carefully evaluate what the actual threshold should be)
      * Duration (minutes): 5
      * Time grain (minutes): 1
      * Time grain statistic: Average
      * Operation: Increase count by
      * Instance count: 1
      * Cool down (minutes): 5

        ![image](./media/10.png)

    1. Repeat the previous step with one minor change to make the Scale in rule.
       1. Set the Metric threshold to trigger scale action: 15
       1. Set the Operation: Decrease count by

            ![image](./media/10a.png)

   3. Now you should have a Scale out and Scale in rule

   4. Instance Limits  Minimum: 1
   5. Instance Limits  Maximum: 1
   6. Instance Limits  Default: 1

        ![image](./media/11.png)


    2. Click Save

        ![image](./media/12.png)

    3. After some time, you can click on the 'Run History' in the tool bar of the auto scale setting to see the observed instance count over time to observe when your app service plan scales out and in.

        ![image](./media/12a.png)

## Query Logs
[Back to Objectives](#objectives)
1. Navigate to https://portal.azure.com
2. Ensure you are in your subscription
3. Navigate to the rg-opex resource group
4. Click on your App Service Web Item Item
5. In the Monitoring Section click on Logs

    ![image](./media/4.png)

6. Close the 'Queries' dialog window.

    ![image](./media/3a.png)

7. Enter the following KQL in the query text box and click Run. Then above the results click on Chart.
    ```kql
        // Response times of requests
        // Avg & 90, 95 and 99 percentile response times (in milliseconds) per App CsHost
        AppServiceHTTPLogs
        | summarize avg(TimeTaken), percentiles(TimeTaken, 90, 95, 99) by CsHost
    ```

    ![image](./media/5.png)

## Reference
* [az monitor app-insights component | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/monitor/log-analytics/workspace?view=azure-cli-latest#az_monitor_log_analytics_workspace_get_shared_keys)
* [az monitor app-insights component create | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/monitor/app-insights/component?view=azure-cli-latest#az_monitor_app_insights_component_create)
* [az appservice plan | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/appservice/plan?view=azure-cli-latest#az_appservice_plan_create)
* [az webapp | Microsoft Docs](https://docs.microsoft.com/en-us/cli/azure/webapp?view=azure-cli-latest#az_webapp_create)
* [Tutorial: Troubleshoot with Azure Monitor - Azure App Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/app-service/tutorial-troubleshoot-monitor#create-azure-resources)
* [CLI: Deploy an app from GitHub - Azure App Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/app-service/scripts/cli-deploy-github?toc=/cli/azure/toc.json)
* [Create a new Azure Monitor Application Insights workspace-based resource - Azure Monitor | Microsoft Docs](https://docs.microsoft.com/en-us/azure/azure-monitor/app/create-workspace-resource)
* [Quickstart: Deploy an ASP.NET web app - Azure App Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/app-service/quickstart-dotnetcore?tabs=netcore31&pivots=development-environment-cli#publish-your-web-app)
