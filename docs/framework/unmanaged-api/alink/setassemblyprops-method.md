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
ms.openlocfilehash: 180eb1a3129cfcd96668ecfee11947c15c5e0915
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776914"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="3a5cd-102">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="3a5cd-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="3a5cd-103">アセンブリレベルのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a5cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a5cd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a5cd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a5cd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3a5cd-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3a5cd-107">プロパティを定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-107">File that defines the property.</span></span> <span data-ttu-id="3a5cd-108">がバインドされ`AssemblyID`ていない .netmodule を示していない場合は、NULL にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="3a5cd-109">変更するオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="3a5cd-110">オプションの新しい値。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a5cd-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a5cd-111">Return Value</span></span>  
 <span data-ttu-id="3a5cd-112">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a5cd-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a5cd-113">Requirements</span></span>  
 <span data-ttu-id="3a5cd-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a5cd-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a5cd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a5cd-115">See also</span></span>

- [<span data-ttu-id="3a5cd-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a5cd-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3a5cd-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a5cd-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3a5cd-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="3a5cd-118">ALink API</span></span>](index.md)
