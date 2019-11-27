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
ms.openlocfilehash: 4bfad8b985a8ef059031464e99a8004842b276c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445573"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="8fc27-102">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="8fc27-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="8fc27-103">アセンブリレベルのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8fc27-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc27-104">構文</span><span class="sxs-lookup"><span data-stu-id="8fc27-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fc27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8fc27-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8fc27-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="8fc27-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8fc27-107">プロパティを定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="8fc27-107">File that defines the property.</span></span> <span data-ttu-id="8fc27-108">`AssemblyID` がバインドされていない .netmodule を示していない場合は NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fc27-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="8fc27-109">変更するオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="8fc27-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="8fc27-110">オプションの新しい値。</span><span class="sxs-lookup"><span data-stu-id="8fc27-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fc27-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8fc27-111">Return Value</span></span>  
 <span data-ttu-id="8fc27-112">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="8fc27-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc27-113">要件</span><span class="sxs-lookup"><span data-stu-id="8fc27-113">Requirements</span></span>  
 <span data-ttu-id="8fc27-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="8fc27-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc27-115">参照</span><span class="sxs-lookup"><span data-stu-id="8fc27-115">See also</span></span>

- [<span data-ttu-id="8fc27-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fc27-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8fc27-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fc27-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8fc27-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="8fc27-118">ALink API</span></span>](index.md)
