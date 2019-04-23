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
ms.openlocfilehash: 589bd7b2132693c89dc10ae1a5c8d0bf52ed481e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218993"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="573ca-102">SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="573ca-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="573ca-103">アセンブリ レベルのプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="573ca-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="573ca-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="573ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="573ca-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="573ca-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="573ca-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="573ca-107">プロパティを定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="573ca-107">File that defines the property.</span></span> <span data-ttu-id="573ca-108">場合に NULL が`AssemblyID`バインドされていない netmodule では示されません。</span><span class="sxs-lookup"><span data-stu-id="573ca-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="573ca-109">変更することを示します。</span><span class="sxs-lookup"><span data-stu-id="573ca-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="573ca-110">オプションの新しい値。</span><span class="sxs-lookup"><span data-stu-id="573ca-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="573ca-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="573ca-111">Return Value</span></span>  
 <span data-ttu-id="573ca-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="573ca-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="573ca-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="573ca-113">Requirements</span></span>  
 <span data-ttu-id="573ca-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="573ca-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573ca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="573ca-115">See also</span></span>

- [<span data-ttu-id="573ca-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="573ca-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="573ca-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="573ca-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="573ca-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="573ca-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
