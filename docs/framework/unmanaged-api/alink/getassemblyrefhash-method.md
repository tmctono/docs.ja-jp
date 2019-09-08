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
ms.openlocfilehash: d19eebaa3aa0ebb6f9807f0cf277b7ed6183c148
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777195"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="9bdce-102">GetAssemblyRefHash メソッド</span><span class="sxs-lookup"><span data-stu-id="9bdce-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="9bdce-103">指定されたアセンブリのハッシュ blob を取得します。</span><span class="sxs-lookup"><span data-stu-id="9bdce-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bdce-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bdce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bdce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9bdce-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="9bdce-106">ハッシュが参照するアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="9bdce-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="9bdce-107">結果のハッシュ blob を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9bdce-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="9bdce-108">ハッシュ blob のサイズをバイト単位で受信します。</span><span class="sxs-lookup"><span data-stu-id="9bdce-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bdce-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9bdce-109">Return Value</span></span>  
 <span data-ttu-id="9bdce-110">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="9bdce-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bdce-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9bdce-111">Requirements</span></span>  
 <span data-ttu-id="9bdce-112">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="9bdce-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bdce-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bdce-113">See also</span></span>

- [<span data-ttu-id="9bdce-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bdce-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9bdce-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bdce-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9bdce-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="9bdce-116">ALink API</span></span>](index.md)
