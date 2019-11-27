---
title: AddImport メソッド
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
ms.openlocfilehash: 52e52ac62e2dcfeb182da3014a863409f640274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446658"
---
# <a name="addimport-method"></a><span data-ttu-id="8bd62-102">AddImport メソッド</span><span class="sxs-lookup"><span data-stu-id="8bd62-102">AddImport Method</span></span>
<span data-ttu-id="8bd62-103">アセンブリにインポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="8bd62-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd62-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bd62-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bd62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bd62-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8bd62-106">補強するアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="8bd62-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="8bd62-107">インポートするファイルの[Importfile メソッド](importfile-method.md)から取得された一意の ID。</span><span class="sxs-lookup"><span data-stu-id="8bd62-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8bd62-108">`ffContainsNoMetaData` や `ffWriteable`などの COM + FileDef フラグ。</span><span class="sxs-lookup"><span data-stu-id="8bd62-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="8bd62-109">`dwFlags` は、の[メソッド](../metadata/imetadataassemblyemit-definefile-method.md)に渡されます。</span><span class="sxs-lookup"><span data-stu-id="8bd62-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="8bd62-110">結果ファイルの ID を受け取るトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8bd62-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bd62-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8bd62-111">Return Value</span></span>  
 <span data-ttu-id="8bd62-112">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="8bd62-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd62-113">要件</span><span class="sxs-lookup"><span data-stu-id="8bd62-113">Requirements</span></span>  
 <span data-ttu-id="8bd62-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="8bd62-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd62-115">参照</span><span class="sxs-lookup"><span data-stu-id="8bd62-115">See also</span></span>

- [<span data-ttu-id="8bd62-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bd62-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8bd62-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bd62-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8bd62-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="8bd62-118">ALink API</span></span>](index.md)
