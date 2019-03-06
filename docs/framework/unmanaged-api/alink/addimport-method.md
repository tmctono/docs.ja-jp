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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 261d80caa43ec478d3a3a33acdebcc1bfcfde8cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500708"
---
# <a name="addimport-method"></a><span data-ttu-id="e705c-102">AddImport メソッド</span><span class="sxs-lookup"><span data-stu-id="e705c-102">AddImport Method</span></span>
<span data-ttu-id="e705c-103">アセンブリにインポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="e705c-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e705c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e705c-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e705c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e705c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e705c-106">追加する対象のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e705c-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="e705c-107">一意の ID の取得から[ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)ファイルをインポートするのです。</span><span class="sxs-lookup"><span data-stu-id="e705c-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e705c-108">COM + FileDef フラグなど`ffContainsNoMetaData`と`ffWriteable`します。</span><span class="sxs-lookup"><span data-stu-id="e705c-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="e705c-109">`dwFlags` 渡される[DefineFile メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="e705c-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="e705c-110">結果のファイルの ID を受け取るトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e705c-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e705c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e705c-111">Return Value</span></span>  
 <span data-ttu-id="e705c-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="e705c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e705c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e705c-113">Requirements</span></span>  
 <span data-ttu-id="e705c-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="e705c-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e705c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e705c-115">See also</span></span>
- [<span data-ttu-id="e705c-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e705c-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e705c-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e705c-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e705c-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="e705c-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
