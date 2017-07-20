```blade
@php
    $local = LaravelLocalization::getCurrentLocale() == LaravelLocalization::getDefaultLocale() && LaravelLocalization::hideDefaultLocaleInURL()
    ? '' : '/'.LaravelLocalization::getCurrentLocale();
@endphp

@section('footer')
    <script>
        const media_root_url = {!! json_encode($local.config('mediaManager.root_url')) !!}
        const warningClass = 'is-warning'
        const errorClass = 'is-danger'
    </script>
    <script src="{{ mix("assets/vendor/MediaManager/script.js") }}"></script>
@endsection
```
