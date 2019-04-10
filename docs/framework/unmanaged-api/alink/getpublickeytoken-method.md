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
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215769"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="73458-102">GetPublicKeyToken メソッド</span><span class="sxs-lookup"><span data-stu-id="73458-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="73458-103">指定したキー ファイルまたはキー コンテナーの公開キー トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="73458-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73458-104">構文</span><span class="sxs-lookup"><span data-stu-id="73458-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="73458-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73458-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="73458-106">キーのファイル名。</span><span class="sxs-lookup"><span data-stu-id="73458-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="73458-107">キー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="73458-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="73458-108">キー トークンが格納されるアドレスです。</span><span class="sxs-lookup"><span data-stu-id="73458-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="73458-109">バイト単位で示されるバッファーのサイズを指定`pvPublicKeyToken`します。</span><span class="sxs-lookup"><span data-stu-id="73458-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="73458-110">戻り時に、実際の使用バイト数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73458-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73458-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="73458-111">Return Value</span></span>  
 <span data-ttu-id="73458-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="73458-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73458-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="73458-113">Requirements</span></span>  
 <span data-ttu-id="73458-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="73458-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73458-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="73458-115">See also</span></span>

- [<span data-ttu-id="73458-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73458-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="73458-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73458-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="73458-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="73458-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
