---
title: CreateALink 関数
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790041"
---
# <a name="createalink-function"></a><span data-ttu-id="a05dd-102">CreateALink 関数</span><span class="sxs-lookup"><span data-stu-id="a05dd-102">CreateALink Function</span></span>
<span data-ttu-id="a05dd-103">アセンブリ リンカーのインスタンスを作成し、指定したインターフェイスへのポインターを設定します。</span><span class="sxs-lookup"><span data-stu-id="a05dd-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a05dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="a05dd-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a05dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a05dd-105">Parameters</span></span>  
  
|<span data-ttu-id="a05dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a05dd-106">Parameter</span></span>|<span data-ttu-id="a05dd-107">説明</span><span class="sxs-lookup"><span data-stu-id="a05dd-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="a05dd-108">アセンブリ リンカー インターフェイスの 1 つの物理名。</span><span class="sxs-lookup"><span data-stu-id="a05dd-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="a05dd-109">正常に完了へのポインターを格納する場所、`riid`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a05dd-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a05dd-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a05dd-110">Requirements</span></span>  
 <span data-ttu-id="a05dd-111">**ライブラリ**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="a05dd-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05dd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a05dd-112">See also</span></span>

- [<span data-ttu-id="a05dd-113">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="a05dd-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
