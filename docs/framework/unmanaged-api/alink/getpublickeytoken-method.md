---
title: GetPublicKeyToken メソッド
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 158ecc036d56e2ad9a3fa650677c04ebcbfd7696
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777217"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="f5a44-102">GetPublicKeyToken メソッド</span><span class="sxs-lookup"><span data-stu-id="f5a44-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="f5a44-103">指定されたキーキーまたはキーコンテナーの公開キートークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5a44-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a44-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5a44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a44-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5a44-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="f5a44-106">キーのファイル名。</span><span class="sxs-lookup"><span data-stu-id="f5a44-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="f5a44-107">キーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="f5a44-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="f5a44-108">キートークンを格納するアドレス。</span><span class="sxs-lookup"><span data-stu-id="f5a44-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="f5a44-109">によって`pvPublicKeyToken`示されるバッファーのサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5a44-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="f5a44-110">戻り時には、実際に使用されたバイト数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5a44-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a44-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5a44-111">Return Value</span></span>  
 <span data-ttu-id="f5a44-112">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="f5a44-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a44-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="f5a44-113">Requirements</span></span>  
 <span data-ttu-id="f5a44-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5a44-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a44-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5a44-115">See also</span></span>

- [<span data-ttu-id="f5a44-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5a44-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f5a44-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5a44-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f5a44-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="f5a44-118">ALink API</span></span>](index.md)
