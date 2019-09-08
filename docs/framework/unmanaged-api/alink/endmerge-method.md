---
title: EndMerge メソッド
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88f594117fffedb6acafef26a9e834dd951ea5bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787534"
---
# <a name="endmerge-method"></a><span data-ttu-id="61ccc-102">EndMerge メソッド</span><span class="sxs-lookup"><span data-stu-id="61ccc-102">EndMerge Method</span></span>
<span data-ttu-id="61ccc-103">すべてのカスタム属性が生成スコープにマージされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="61ccc-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ccc-104">構文</span><span class="sxs-lookup"><span data-stu-id="61ccc-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="61ccc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61ccc-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="61ccc-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="61ccc-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61ccc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="61ccc-107">Return Value</span></span>  
 <span data-ttu-id="61ccc-108">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="61ccc-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61ccc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="61ccc-109">Requirements</span></span>  
 <span data-ttu-id="61ccc-110">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="61ccc-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ccc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="61ccc-111">See also</span></span>

- [<span data-ttu-id="61ccc-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61ccc-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="61ccc-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61ccc-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="61ccc-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="61ccc-114">ALink API</span></span>](index.md)
