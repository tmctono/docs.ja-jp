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
ms.openlocfilehash: c68f43ce2f79ee6e4ec44ce4b2f0dbfb1c1185fa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433876"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="acb31-102">GetAssemblyRefHash メソッド</span><span class="sxs-lookup"><span data-stu-id="acb31-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="acb31-103">指定されたアセンブリのハッシュ blob を取得します。</span><span class="sxs-lookup"><span data-stu-id="acb31-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb31-104">構文</span><span class="sxs-lookup"><span data-stu-id="acb31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="acb31-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acb31-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="acb31-106">ハッシュが参照するアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="acb31-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="acb31-107">結果のハッシュ blob を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="acb31-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="acb31-108">ハッシュ blob のサイズをバイト単位で受信します。</span><span class="sxs-lookup"><span data-stu-id="acb31-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acb31-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="acb31-109">Return Value</span></span>  
 <span data-ttu-id="acb31-110">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="acb31-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb31-111">要件</span><span class="sxs-lookup"><span data-stu-id="acb31-111">Requirements</span></span>  
 <span data-ttu-id="acb31-112">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="acb31-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb31-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb31-113">See also</span></span>

- [<span data-ttu-id="acb31-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acb31-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="acb31-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acb31-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="acb31-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="acb31-116">ALink API</span></span>](index.md)
