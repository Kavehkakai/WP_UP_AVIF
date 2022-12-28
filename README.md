# WP_UP_AVIF

<?php
/**
 * WordPress enable Import AVIF file
 *
 * @see https://developer.wordpress.org/reference/functions/wp_check_filetype_and_ext/
 */
function barrd_enable_avif_types( $types, $file, $filename, $mimes ) {
	if ( false !== strpos( $filename, '.avif' ) ) {
		$types['ext']  = 'avif';
		$types['type'] = 'image/avif';
	}

	return $types;
}
add_filter( 'wp_check_filetype_and_ext', 'barrd_enable_avif_types', 10, 4 );

/**
 * Add mime type
 *
 * @see https://developer.wordpress.org/reference/hooks/upload_mimes/
 */
function barrd_enable_avif_mime( $mimes ) {
	$mimes['avif'] = 'image/avif';

	return $mimes;
}
add_filter( 'upload_mimes', 'barrd_enable_avif_mime' );
