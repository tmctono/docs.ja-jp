---
ms.service: multiple
ms.date: 9/20/2018
ms.topic: include
ms.openlocfilehash: bfa7bcefff45bc325d7bba3aa2b9b3a8f0d439fa
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433158"
---
<span data-ttu-id="d0f54-101">`azureauth.json` という名前でテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0f54-101">Create a text file named `azureauth.json`.</span></span> <span data-ttu-id="d0f54-102">サービス プリンシパル作成時の JSON 出力を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d0f54-102">Paste the JSON output from when you created the service principal.</span></span>

<span data-ttu-id="d0f54-103">このファイルは、コードで読み取ることができるシステム上の安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="d0f54-103">Save this file in a secure location on your system where your code can read it.</span></span> <span data-ttu-id="d0f54-104">PowerShell を使用して、`AZURE_AUTH_LOCATION` という名前の環境変数を設定します。このときに、保存したテキスト ファイルの完全なパスも指定します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d0f54-104">Use PowerShell to set an environment variable named `AZURE_AUTH_LOCATION` with the full path to the file, for example:</span></span>

```powershell
[Environment]::SetEnvironmentVariable("AZURE_AUTH_LOCATION", "C:\src\azureauth.json", "User")
```
