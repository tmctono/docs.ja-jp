---
title: ImportTypes2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f14822a58f3982d6f9fee1328c10b960657c056f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753505"
---
# <a name="importtypes2-method"></a><span data-ttu-id="ec79c-102">ImportTypes2 メソッド</span><span class="sxs-lookup"><span data-stu-id="ec79c-102">ImportTypes2 Method</span></span>
<span data-ttu-id="ec79c-103">型のインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="ec79c-103">Initiates the import of types.</span></span> <span data-ttu-id="ec79c-104">使用してインポートする各スコープから種類のインポートを開始するには、このメソッドを呼び出す[ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec79c-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec79c-105">構文</span><span class="sxs-lookup"><span data-stu-id="ec79c-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec79c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec79c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ec79c-107">インポートするアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="ec79c-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ec79c-108">インポート元のファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="ec79c-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ec79c-109">インポート元の 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="ec79c-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="ec79c-110">指定されたスコープで、型の列挙子のハンドルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ec79c-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ec79c-111">必要に応じて受信[IMetaDataImport2 インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ec79c-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="ec79c-112">必要に応じて、指定したスコープの種類の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ec79c-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec79c-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="ec79c-113">Return Value</span></span>  
 <span data-ttu-id="ec79c-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="ec79c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec79c-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="ec79c-115">Requirements</span></span>  
 <span data-ttu-id="ec79c-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec79c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec79c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec79c-117">See also</span></span>

- [<span data-ttu-id="ec79c-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec79c-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ec79c-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec79c-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ec79c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="ec79c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
