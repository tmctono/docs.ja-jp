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
ms.openlocfilehash: 1e9f51799ea56cb1e5819d708a0e4a8136a94f3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741484"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="1b519-102">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="1b519-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="1b519-103">アセンブリ レベルのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1b519-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b519-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b519-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b519-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b519-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1b519-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="1b519-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1b519-107">プロパティを定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="1b519-107">File that defines the property.</span></span> <span data-ttu-id="1b519-108">場合に NULL が`AssemblyID`バインドされていない netmodule では示されません。</span><span class="sxs-lookup"><span data-stu-id="1b519-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="1b519-109">変更することを示します。</span><span class="sxs-lookup"><span data-stu-id="1b519-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="1b519-110">オプションの新しい値。</span><span class="sxs-lookup"><span data-stu-id="1b519-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b519-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="1b519-111">Return Value</span></span>  
 <span data-ttu-id="1b519-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="1b519-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b519-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="1b519-113">Requirements</span></span>  
 <span data-ttu-id="1b519-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b519-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b519-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b519-115">See also</span></span>

- [<span data-ttu-id="1b519-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b519-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1b519-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b519-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1b519-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="1b519-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
