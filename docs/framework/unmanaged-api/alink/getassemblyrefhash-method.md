---
title: GetAssemblyRefHash メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fa8d42f9e849db6a02f6c62b37e04cf5dee016e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119653"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="090f5-102">GetAssemblyRefHash メソッド</span><span class="sxs-lookup"><span data-stu-id="090f5-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="090f5-103">指定されたアセンブリ ハッシュ blob を取得します。</span><span class="sxs-lookup"><span data-stu-id="090f5-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="090f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="090f5-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="090f5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="090f5-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="090f5-106">ハッシュが参照するアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="090f5-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="090f5-107">結果として得られるハッシュ blob を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="090f5-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="090f5-108">ハッシュ blob のバイト単位のサイズを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="090f5-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="090f5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="090f5-109">Return Value</span></span>  
 <span data-ttu-id="090f5-110">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="090f5-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="090f5-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="090f5-111">Requirements</span></span>  
 <span data-ttu-id="090f5-112">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="090f5-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="090f5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="090f5-113">See also</span></span>

- [<span data-ttu-id="090f5-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="090f5-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="090f5-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="090f5-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="090f5-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="090f5-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
