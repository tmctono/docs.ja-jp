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
ms.openlocfilehash: 24f7e2d5a547b78ceb4808feaf581c6f49807cf7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787617"
---
# <a name="createalink-function"></a><span data-ttu-id="5a111-102">CreateALink 関数</span><span class="sxs-lookup"><span data-stu-id="5a111-102">CreateALink Function</span></span>
<span data-ttu-id="5a111-103">アセンブリリンカーのインスタンスを作成し、指定したインターフェイスへのポインターを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a111-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a111-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a111-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a111-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a111-105">Parameters</span></span>  
  
|<span data-ttu-id="5a111-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a111-106">Parameter</span></span>|<span data-ttu-id="5a111-107">説明</span><span class="sxs-lookup"><span data-stu-id="5a111-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="5a111-108">アセンブリリンカーインターフェイスの1つの物理名。</span><span class="sxs-lookup"><span data-stu-id="5a111-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="5a111-109">正常に完了した場所には、 `riid`インターフェイスへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a111-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a111-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a111-110">Requirements</span></span>  
 <span data-ttu-id="5a111-111">**ライブラリ**: alink</span><span class="sxs-lookup"><span data-stu-id="5a111-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a111-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a111-112">See also</span></span>

- [<span data-ttu-id="5a111-113">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="5a111-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
