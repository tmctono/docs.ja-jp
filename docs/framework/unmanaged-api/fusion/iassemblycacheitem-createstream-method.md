---
title: IAssemblyCacheItem::CreateStream メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 380e248c8c4e3407fff868cdd9a5c63b63e50c69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697514"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="af3f3-102">IAssemblyCacheItem::CreateStream メソッド</span><span class="sxs-lookup"><span data-stu-id="af3f3-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="af3f3-103">指定した名前と形式を使用するストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="af3f3-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="af3f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="af3f3-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="af3f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af3f3-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="af3f3-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="af3f3-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="af3f3-107">[in]作成されるストリームの名前。</span><span class="sxs-lookup"><span data-stu-id="af3f3-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="af3f3-108">[in]ストリーミングされるように、ファイルの形式です。</span><span class="sxs-lookup"><span data-stu-id="af3f3-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="af3f3-109">[in]形式固有のものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="af3f3-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="af3f3-110">[out]返されるのアドレスへのポインター [IStream](/windows/desktop/api/objidl/nn-objidl-istream)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="af3f3-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="af3f3-111">[in、省略可能]によって参照されるストリームの最大サイズ`ppIStream`します。</span><span class="sxs-lookup"><span data-stu-id="af3f3-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="af3f3-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="af3f3-112">Requirements</span></span>

<span data-ttu-id="af3f3-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af3f3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="af3f3-114">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="af3f3-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="af3f3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af3f3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="af3f3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af3f3-116">See also</span></span>

- [<span data-ttu-id="af3f3-117">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af3f3-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)