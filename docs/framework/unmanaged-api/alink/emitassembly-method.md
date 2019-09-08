---
title: EmitAssembly メソッド
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2adf53d1e29fda077cdcf7b79891f6271993109
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787583"
---
# <a name="emitassembly-method"></a><span data-ttu-id="3e8c4-102">EmitAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="3e8c4-102">EmitAssembly Method</span></span>
<span data-ttu-id="3e8c4-103">アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-103">Creates the assembly.</span></span> <span data-ttu-id="3e8c4-104">アセンブリファイルを除く他のすべてのファイルが閉じられた後に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="3e8c4-105">バインドされていないモジュールを生成する場合は、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8c4-106">構文</span><span class="sxs-lookup"><span data-stu-id="3e8c4-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e8c4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e8c4-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3e8c4-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e8c4-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3e8c4-109">Return Value</span></span>  
 <span data-ttu-id="3e8c4-110">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e8c4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e8c4-111">Requirements</span></span>  
 <span data-ttu-id="3e8c4-112">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8c4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e8c4-113">See also</span></span>

- [<span data-ttu-id="3e8c4-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e8c4-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3e8c4-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e8c4-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3e8c4-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="3e8c4-116">ALink API</span></span>](index.md)
