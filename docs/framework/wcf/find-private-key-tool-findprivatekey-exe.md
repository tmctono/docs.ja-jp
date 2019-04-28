---
title: 秘密キー検索ツール (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 8f156cbb2f4fad8d51e356bd4dee2d72d9397ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929585"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="15a8b-102">秘密キー検索ツール (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="15a8b-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="15a8b-103">このコマンド ライン ツールを使用して、証明書ストアから秘密キーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="15a8b-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="15a8b-104">たとえば、 *FindPrivateKey.exe*証明書ストアに特定の X.509 証明書に関連付けられている秘密キー ファイルの名前と場所を検索するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="15a8b-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15a8b-105">FindPrivateKey ツールは、WCF のサンプルとして付属しています。</span><span class="sxs-lookup"><span data-stu-id="15a8b-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="15a8b-106">サンプルの検索場所と構築方法の詳細については、次を参照してください。 [FindPrivateKey](./samples/findprivatekey.md)します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="15a8b-107">構文</span><span class="sxs-lookup"><span data-stu-id="15a8b-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="15a8b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="15a8b-108">Remarks</span></span>

<span data-ttu-id="15a8b-109">次の表では、秘密キー検索ツール (FindPrivateKey.exe) で使用できる引数とオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="15a8b-110">引数</span><span class="sxs-lookup"><span data-stu-id="15a8b-110">Argument</span></span>|<span data-ttu-id="15a8b-111">説明</span><span class="sxs-lookup"><span data-stu-id="15a8b-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="15a8b-112">証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="15a8b-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="15a8b-113">証明書ストアの場所。</span><span class="sxs-lookup"><span data-stu-id="15a8b-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="15a8b-114">オプション</span><span class="sxs-lookup"><span data-stu-id="15a8b-114">Option</span></span>|<span data-ttu-id="15a8b-115">説明</span><span class="sxs-lookup"><span data-stu-id="15a8b-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="15a8b-116">`/n <` *subjectName* `>`</span><span class="sxs-lookup"><span data-stu-id="15a8b-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="15a8b-117">証明書のサブジェクト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="15a8b-118">`/t <` *thumbprint* `>`</span><span class="sxs-lookup"><span data-stu-id="15a8b-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="15a8b-119">証明書のサムプリントを指定します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="15a8b-120">Certmgr.exe を使用して証明書のサムプリントを取得します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="15a8b-121">ファイル名だけを出力します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="15a8b-122">ディレクトリだけを出力します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="15a8b-123">絶対ファイル名を出力します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="15a8b-124">使用例</span><span class="sxs-lookup"><span data-stu-id="15a8b-124">Examples</span></span>

<span data-ttu-id="15a8b-125">次のコマンドは、John Doe の秘密キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="15a8b-126">次のコマンドは、ローカル コンピューター用の秘密キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="15a8b-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```