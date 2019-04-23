---
title: ImportTypes メソッド
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 622e57aedf6c49e95dc2d7e40ba598361b3e6a26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222862"
---
# <a name="importtypes-method"></a><span data-ttu-id="b44ec-102">ImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="b44ec-102">ImportTypes Method</span></span>
<span data-ttu-id="b44ec-103">使用してインポートする各スコープの種類のインポートを開始する[ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="b44ec-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="b44ec-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b44ec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b44ec-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b44ec-106">インポート先のアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="b44ec-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b44ec-107">インポートするファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="b44ec-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="b44ec-108">インポートする 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="b44ec-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="b44ec-109">このスコープの種類の列挙子のハンドルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b44ec-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="b44ec-110">必要に応じて受信[IMetaDataImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="b44ec-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="b44ec-111">必要に応じて指定のスコープ内の種類の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b44ec-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b44ec-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="b44ec-112">Return Value</span></span>  
 <span data-ttu-id="b44ec-113">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b44ec-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b44ec-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="b44ec-114">Requirements</span></span>  
 <span data-ttu-id="b44ec-115">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="b44ec-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b44ec-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b44ec-116">See also</span></span>

- [<span data-ttu-id="b44ec-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b44ec-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b44ec-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b44ec-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b44ec-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="b44ec-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
