---
title: SetAssemblyProps メソッド
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc9ca5d9533a6c4a297155a47ac0061f1232d242
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481104"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="2bda6-102">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="2bda6-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="2bda6-103">アセンブリ レベルのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2bda6-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bda6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bda6-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bda6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bda6-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2bda6-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="2bda6-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2bda6-107">プロパティを定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="2bda6-107">File that defines the property.</span></span> <span data-ttu-id="2bda6-108">場合に NULL が`AssemblyID`バインドされていない netmodule では示されません。</span><span class="sxs-lookup"><span data-stu-id="2bda6-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="2bda6-109">変更することを示します。</span><span class="sxs-lookup"><span data-stu-id="2bda6-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="2bda6-110">オプションの新しい値。</span><span class="sxs-lookup"><span data-stu-id="2bda6-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bda6-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bda6-111">Return Value</span></span>  
 <span data-ttu-id="2bda6-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="2bda6-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bda6-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bda6-113">Requirements</span></span>  
 <span data-ttu-id="2bda6-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="2bda6-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bda6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bda6-115">See also</span></span>
- [<span data-ttu-id="2bda6-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bda6-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2bda6-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bda6-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2bda6-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="2bda6-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
