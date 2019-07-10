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
ms.openlocfilehash: a51e8c83d0949f68a41f6a4e10396adbc4f3c9c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741894"
---
# <a name="getfiledef-method"></a><span data-ttu-id="a2438-102">GetFileDef メソッド</span><span class="sxs-lookup"><span data-stu-id="a2438-102">GetFileDef Method</span></span>
<span data-ttu-id="a2438-103">(ALink によって割り当てられたトークン) ではなくメタデータで使用される実際の FileDef トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="a2438-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2438-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2438-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2438-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2438-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a2438-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="a2438-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="a2438-107">追加されたファイルのトークン AddFile メソッドまたは AddImport メソッドから取得します。</span><span class="sxs-lookup"><span data-stu-id="a2438-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="a2438-108">FileDef トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a2438-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2438-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a2438-109">Return Value</span></span>  
 <span data-ttu-id="a2438-110">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a2438-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2438-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2438-111">Requirements</span></span>  
 <span data-ttu-id="a2438-112">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2438-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2438-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2438-113">See also</span></span>

- [<span data-ttu-id="a2438-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2438-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a2438-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2438-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a2438-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="a2438-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
