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
ms.openlocfilehash: 6a561205602920123176bd421ca2ef1b601166c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426054"
---
# <a name="getfiledef-method"></a><span data-ttu-id="43453-102">GetFileDef メソッド</span><span class="sxs-lookup"><span data-stu-id="43453-102">GetFileDef Method</span></span>
<span data-ttu-id="43453-103">ALink によって割り当てられたトークンとは対照的に、メタデータで使用される実際の FileDef トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="43453-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43453-104">構文</span><span class="sxs-lookup"><span data-stu-id="43453-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="43453-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43453-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="43453-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="43453-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="43453-107">AddFile メソッドまたは AddImport メソッドから取得された追加ファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="43453-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="43453-108">FileDef トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="43453-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43453-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="43453-109">Return Value</span></span>  
 <span data-ttu-id="43453-110">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="43453-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43453-111">要件</span><span class="sxs-lookup"><span data-stu-id="43453-111">Requirements</span></span>  
 <span data-ttu-id="43453-112">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="43453-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43453-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="43453-113">See also</span></span>

- [<span data-ttu-id="43453-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43453-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="43453-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43453-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="43453-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="43453-116">ALink API</span></span>](index.md)
