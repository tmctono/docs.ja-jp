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
ms.openlocfilehash: bf7b54ab7a2318e8194bf39dbe41b864633ddb43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212911"
---
# <a name="emitassembly-method"></a><span data-ttu-id="bf1aa-102">EmitAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="bf1aa-102">EmitAssembly Method</span></span>
<span data-ttu-id="bf1aa-103">アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf1aa-103">Creates the assembly.</span></span> <span data-ttu-id="bf1aa-104">アセンブリ ファイルを除くその他のすべてのファイルが閉じられた後は、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bf1aa-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="bf1aa-105">バインドされていないモジュールを生成するときに、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="bf1aa-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf1aa-106">構文</span><span class="sxs-lookup"><span data-stu-id="bf1aa-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf1aa-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf1aa-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bf1aa-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="bf1aa-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf1aa-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bf1aa-109">Return Value</span></span>  
 <span data-ttu-id="bf1aa-110">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="bf1aa-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf1aa-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf1aa-111">Requirements</span></span>  
 <span data-ttu-id="bf1aa-112">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="bf1aa-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1aa-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf1aa-113">See also</span></span>

- [<span data-ttu-id="bf1aa-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf1aa-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="bf1aa-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf1aa-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="bf1aa-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="bf1aa-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
