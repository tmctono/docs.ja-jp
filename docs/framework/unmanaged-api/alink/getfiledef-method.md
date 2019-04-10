---
title: GetFileDef メソッド
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9153c9b3735e265d59ba072f747c92434c95d9ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184497"
---
# <a name="getfiledef-method"></a><span data-ttu-id="f5f1f-102">GetFileDef メソッド</span><span class="sxs-lookup"><span data-stu-id="f5f1f-102">GetFileDef Method</span></span>
<span data-ttu-id="f5f1f-103">(ALink によって割り当てられたトークン) ではなくメタデータで使用される実際の FileDef トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5f1f-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5f1f-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5f1f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5f1f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f5f1f-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="f5f1f-107">追加されたファイルのトークン AddFile メソッドまたは AddImport メソッドから取得します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="f5f1f-108">FileDef トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5f1f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5f1f-109">Return Value</span></span>  
 <span data-ttu-id="f5f1f-110">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5f1f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f5f1f-111">Requirements</span></span>  
 <span data-ttu-id="f5f1f-112">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5f1f-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f1f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5f1f-113">See also</span></span>

- [<span data-ttu-id="f5f1f-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5f1f-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f5f1f-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5f1f-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f5f1f-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="f5f1f-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
